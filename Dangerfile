# TODO: какие правила можно добавить
# Задачи на добавление новых правил в Danger в этом эпике https://jira.tcsbank.ru/browse/MBIOS-23157

def check_for_new_files_in_important_directories
  checking_depth = 3
  dirs_to_enter = {
      0 => ["./LocalPods"],
      1 => ["./LocalPods/Feature", "./LocalPods/Common"]
  }
  
  new_important_files = []
  git.added_files.each { |added_file|
    passed_path = "."
    puts("start #{added_file}")
    added_file_local_path = "./" + added_file
    added_file.split("/").first(checking_depth).each_with_index { |part, index|
        files = Dir.entries(passed_path).map { |path| passed_path + "/" + path }.reject { |path| path == added_file_local_path }
        puts("#{files}")
        passed_path += "/#{part}"
        if !dirs_to_enter[index]&.include?(passed_path)
          new_important_files << added_file unless files.include?(part)
        end
    }
  }
  puts("wtf #{new_important_files}")
  return if new_important_files.empty?

  new_important_files.each { |file| 
      warn "Создан новый файл #{file}, необходимо добавить ответственных в approvers.yml"
  }
end

# Вызовы основных проверок
check_for_new_files_in_important_directories