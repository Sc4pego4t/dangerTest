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
            all_files_in_directory = Dir.glob(passed_path+"**/*").reject { |fn| File.directory?(fn) }
            # Проверяем, все ли файлы в папке были созданы в этом PR
            is_subset = (all_files_in_directory - added_files_local).empty?
            is_new_important_file = is_subset
          end
          new_important_files << added_file if is_new_important_file
          break
        end
    }
  }

  new_important_files.each { |file| 
      warn "Создан новый файл #{file}, необходимо добавить ответственных в approvers.yml"
  } unless new_important_files.empty?
end

# Вызовы основных проверок
check_for_new_files_in_important_directories