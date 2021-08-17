# TODO: какие правила можно добавить
# Задачи на добавление новых правил в Danger в этом эпике https://jira.tcsbank.ru/browse/MBIOS-23157

def check_for_new_files_in_important_directories
  passed_path = "."
  checking_depth = 3
  dirs_to_enter = {
      0 => ["./LocalPods"],
      1 => ["./LocalPods/Feature", "./LocalPods/Common"]
  }

  warn "#{git.added_files}"

  new_important_files = []
  git.added_files.each { |added_file|
    added_file.split("/").first(checking_depth).each_with_index { |part, index|
        new_important_files << added_file unless Dir.entries(passed_path).include?(part)
        passed_path += "/#{part}"
        break unless dirs_to_enter[index]&.include?(passed_path)
    }
  }

  return if new_important_files.empty?

  new_important_files.each { |file| 
      warn "Создан новый файл #{file}, необходимо добавить ответственных в approvers.yml"
  }
end

# Вызовы основных проверок
check_for_new_files_in_important_directories