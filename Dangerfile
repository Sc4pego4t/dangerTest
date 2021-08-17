# TODO: какие правила можно добавить
# Задачи на добавление новых правил в Danger в этом эпике https://jira.tcsbank.ru/browse/MBIOS-23157

def check_for_new_files_in_important_directories
  # Директории в которых нужно проверить что бы не создавался файл (Корневая тоже)
  dirs_to_check = ["./LocalPods", "./LocalPods/Feature", "./LocalPods/Common"]
  
  new_important_files = []
  added_files_local = git.added_files.map { |file| "./" + file }

  git.added_files.each { |added_file|
    passed_path = "."
    added_file.split("/").each { |part|
        passed_path += "/#{part}"

        # Мы должны остановится если путь не находится в dirs_to_check
        if !dirs_to_check.include?(passed_path)
          is_new_important_file = true
          # Если путь на котором мы остановились является директорией
          # То мы должны понять, новая ли это директория или она существовала до этого
          if File.directory?(passed_path)
            # Рекурсивно получаем все файлы в папке
            all_files_in_directory = Dir.glob(passed_path + "/**/*").reject { |fn| File.directory?(fn) }
            # Проверяем, все ли файлы в папке были созданы в этом PR
            is_subset = (all_files_in_directory - added_files_local).empty?
            is_new_important_file = is_subset
          end
          new_important_files << added_file if is_new_important_file
          break
        end
    }
  }

  messages = []
  # Сортируем по убыванию чтобы находить самый длинный substing
  dirs_to_check_sorted = dirs_to_check.sort_by { |str| -str.length }.map { |dir| dir + "/" }
  # Добавляем root чтобы в нем тоже искались файлы
  dirs_to_check_sorted << "./"
  # Этот блок кода нужен чтобы понять, добавилась папка с файлами или просто файл
  new_important_files.map { |file| "./" + file }.each { |important_file|
    important_file_copy = important_file
    dirs_to_check_sorted.each { |check_dir|
      if important_file_copy.include?(check_dir)
        common_part = important_file_copy.slice!(check_dir)
        first_split = important_file_copy.split("/").first
        if File.directory?(common_part + first_split)
          messages << "Создана новая директория #{common_part + first_split}, необходимо добавить ответственных в approvers.yml"
        else
          messages << "Создан новый файл #{important_file}, необходимо добавить ответственных в approvers.yml"
        end
      end
    }
  }
  messages.uniq.sort.each { |message| warn  message }
end

# Вызовы основных проверок
check_for_new_files_in_important_directories