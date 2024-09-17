fastlane documentation
================
# Installation

Make sure you have the latest version of the Xcode command line tools installed:

```
xcode-select --install
```

Install _fastlane_ using
```
[sudo] gem install fastlane -NV
```
or alternatively using `brew install fastlane`

# Available Actions
### deploy_junior_qa_enterprise
```
fastlane deploy_junior_qa_enterprise
```

### deploy_junior_qa_testflight
```
fastlane deploy_junior_qa_testflight
```

### deploy_junior_appstore
```
fastlane deploy_junior_appstore
```

### jira_issues_from_git_commits_changelog
```
fastlane jira_issues_from_git_commits_changelog
```
Collect JIRA issues from changelog git-commits
### jira_issues_resolve_transition
```
fastlane jira_issues_resolve_transition
```
Resolve and set Build Number field for JIRA issues
### get_jira_credentials_if_needed
```
fastlane get_jira_credentials_if_needed
```
Get JIRA credentials
### merge_request_suite
```
fastlane merge_request_suite
```

### run_danger
```
fastlane run_danger
```

### build_and_test
```
fastlane build_and_test
```

### lint
```
fastlane lint
```

### build_for_testing
```
fastlane build_for_testing
```

### run_unit_tests
```
fastlane run_unit_tests
```

### run_ui_tests
```
fastlane run_ui_tests
```
Run UI test

#### Options

* **`test_names`: Comma separated list of UI tests to run (default is 'UITests/UIOnboardingShakeToP2P')
### setup
```
fastlane setup
```

### mb_increment_app_version
```
fastlane mb_increment_app_version
```
Usage: bundle exec fastlane mb_increment_app_version version:6.0.4 --env mobilebank
### mb_increment_build_number
```
fastlane mb_increment_build_number
```

### mb_resolve_podfile_conflicts
```
fastlane mb_resolve_podfile_conflicts
```

### git_pull_target_branch
```
fastlane git_pull_target_branch
```

### update_localization
```
fastlane update_localization
```
Generates localization file
### update_team_localization
```
fastlane update_team_localization
```
Fetch localization by file name. Leave empty for update all
### validate_localization
```
fastlane validate_localization
```
Validate eng and rus localization
### mb_just_build
```
fastlane mb_just_build
```

### mb_long_compile_lines_scan
```
fastlane mb_long_compile_lines_scan
```
Long compile lines scan
### mb_duplicated_pods_scan
```
fastlane mb_duplicated_pods_scan
```

### mb_unused_objc_scan
```
fastlane mb_unused_objc_scan
```

### mb_unused_assets_scan
```
fastlane mb_unused_assets_scan
```
Run unused_assets_scan with options from UnusedAssets.yml
### mb_localization_check
```
fastlane mb_localization_check
```
Run localization_checker with options from LocalizationChecker.yml
### mb_assets_check
```
fastlane mb_assets_check
```
Run assets_checker with options from AssetsChecker.yml
### match_install_development
```
fastlane match_install_development
```
Install development certs and profiles from match repo in READONLY mode. Should be called locally by developers.

Usage:

`bundle exec fastlane match_install_development`
### match_development
```
fastlane match_development
```
By default this lane will install development certs and profiles.

Provisioning profiles will be updated only if new devices were added to Developer portal.

You can force recreate provisioning profiles if use `force:true` option.

Usage:

`bundle exec fastlane match_development`

`bundle exec fastlane match_development force:true`

Make sure to call setup_ci before this lane to use match in readonly mode on CI!

####Options

 * **`force`**: Renew the provisioning profiles. Defaults to false.
### match_enterprise
```
fastlane match_enterprise
```
By default this lane will install enterprise distribution certs and profiles.

You can force recreate provisioning profiles if use `force:true` option.

Usage:

`bundle exec fastlane match_enterprise`

`bundle exec fastlane match_enterprise force:true`

Make sure to call setup_ci before this lane to use match in readonly mode on CI!

####Options

 * **`force`**: Renew the provisioning profiles. Defaults to false.
### match_appstore
```
fastlane match_appstore
```
By default this lane will install appstore distribution certs and profiles.

You can force recreate provisioning profiles if use `force:true` option.

Usage:

`bundle exec fastlane match_appstore`

`bundle exec fastlane match_appstore force:true`

Make sure to call setup_ci before this lane to use match in readonly mode on CI!

####Options

 * **`force`**: Renew the provisioning profiles. Defaults to false.
### match_testflight
```
fastlane match_testflight
```
By default this lane will install appstore QA distribution certs and profiles.

You can force recreate provisioning profiles if use `force:true` option.

Usage:

`bundle exec fastlane match_appstore`

`bundle exec fastlane match_appstore force:true`

Make sure to call setup_ci before this lane to use match in readonly mode on CI!

####Options

 * **`force`**: Renew the provisioning profiles. Defaults to false.
### generate_module
```
fastlane generate_module
```

### mb_apply_automatic_signing_settings
```
fastlane mb_apply_automatic_signing_settings
```

### junior_apply_automatic_signing_settings
```
fastlane junior_apply_automatic_signing_settings
```

### run_diagnostics
```
fastlane run_diagnostics
```
Build with diagnostic logging and generate reports
### diagnostic_build
```
fastlane diagnostic_build
```
Build project with diagnostics options enabled
### statistics_build
```
fastlane statistics_build
```
Build project without tests
### generate_diagnostic_reports
```
fastlane generate_diagnostic_reports
```
Parse xcodebuild log and generate diagnostic reports
### developer_build_and_report
```
fastlane developer_build_and_report
```

### developer_build_test_and_report
```
fastlane developer_build_test_and_report
```

### developer_build_for_testing
```
fastlane developer_build_for_testing
```
Make a clean build-for-testing just like developers do

#### Options

- *'env.DEVELOPER_BUILD_SCHEME'* scheme to build (default is 'MobileBank')
### developer_testing
```
fastlane developer_testing
```
Run test on pre-compiled project just like developers do

#### Options

- *'env.DEVELOPER_BUILD_SCHEME'* scheme to test (default is 'MobileBank')
### parse_activity_log
```
fastlane parse_activity_log
```
Generate xclogparser reports
### build_for_ui_testing
```
fastlane build_for_ui_testing
```

### build_for_ui_testing_emcee
```
fastlane build_for_ui_testing_emcee
```
Сборка проекта для запуска тестов с использованием Emcee
### setup_xctests_report_parser
```
fastlane setup_xctests_report_parser
```
Настройка утилиты XCTestsReportsParser
### run_ui_test_in_parallel
```
fastlane run_ui_test_in_parallel
```
Запуск тестов в параллельном режиме

Запускается на CI для единичного, не разделенного на бакеты запуска.

####Options

 * **`tests`**: Список тестов предназначенных для запуска.

 * **`only_test_configurations`**: Список конфигов, с которыми будут запускаться тесты. По умолчанию используется ["Default"]

 * **`version`**: Версия iOS. Необязательный параметр, по умолчанию используется 14.5

 * **`model`**: Версия симулятора. Необязательный параметр, по умолчанию используется iPhone SE 2

 * **`skip`**: Список тестов, которые будут пропущены. Необязательный параметр, по умолчанию используется 

 * **`is_proxy`**: Параметр, показывающий используем ли мы прокси. По умолчанию используется YES

 * **`is_mock_debug`**: Определяет используется ли debug режим. По умолчанию используется NO

 * **`is_performance_test`**: Параметр, определяющий запускается ли тест команды Производительности. По умолчанию используется NO


### run_testplan_in_parallel
```
fastlane run_testplan_in_parallel
```
Запуск тестплана в параллельном режиме

Запускается на CI для единичного, не разделенного на бакеты запуска.

####Options

 * **`testplan`**: Название тестплана.

 * **`only_test_configurations`**: Список конфигов, с которыми будет запускаться тестплан. По умолчанию используется ["Default"]

 * **`version`**: Версия iOS. Необязательный параметр, по умолчанию используется 14.5

 * **`model`**: Версия симулятора. Необязательный параметр, по умолчанию используется iPhone SE 2

 * **`skip`**: Список тестов, которые будут пропущены. Необязательный параметр, по умолчанию используется 

 * **`is_proxy`**: Параметр, показывающий используем ли мы прокси. По умолчанию используется YES

 * **`is_mock_debug`**: Определяет используется ли debug режим. По умолчанию используется NO

 * **`is_performance_test`**: Параметр, определяющий запускается ли тест команды Производительности. По умолчанию используется NO


### generate_allure_results
```
fastlane generate_allure_results
```
Генерация и отправление результатов прогона в аллюр.

Выполняется после прогона тестов, когда результаты лежат в report/0  и report/1. Выполняются команды xcresults и allurectl

####Options

 * **`token`**: Токен от allure для отправления туда результатов.

 * **`run_name`**: Название рана в allure. Необязательный параметр, по умолчанию используется Emcee run iOS

 * **`allure_project_id`**: Id проекта в allure. Необязательный параметр, по умолчанию используется 90


### send_partial_allure_results
```
fastlane send_partial_allure_results
```
Генерация и отправление результатов прогона в уже созданный ран в аллюр.

Выполняется после прогона тестов, когда результаты лежат в report/0  и report/1. Из артефактов получается json, из которого берется run id

####Options

 * **`token`**: Токен от allure для отправления туда результатов.


### run_ui_range_test_in_parallel
```
fastlane run_ui_range_test_in_parallel
```
Запуск тестов в параллельном режиме с ранжированнием по бакетам. Снапшоты исключены из прогона

Запускается на CI для ночного прогона всех тестов. Содержит ретраи упавших тестов.

####Options

 * **`groups_count`**: Общее количество бакетов на которые будет поделен список.

 * **`group_index`**: Номер запускаемой группы

 * **`only_test_configurations`**: Список конфигов, с которыми будут запускаться тесты. По умолчанию используется ["Default"]

 * **`version`**: Версия iOS. Необязательный параметр, по умолчанию используется 14.5

 * **`model`**: Версия симулятора. Необязательный параметр, по умолчанию используется iPhone SE 2

 * **`skip`**: Список тестов, которые будут пропущены. Необязательный параметр, по умолчанию используется 

 * **`repo_name`**: уникальное имя репозитория проекта. Необязательный параметр, по умолчанию используется mb-iphone

 * **`team`**: Название фиче-тимы, тесты которой будут запущены.


### disable_tls
```
fastlane disable_tls
```
Изменение plist'ов для активации swifter

####Options

 * **`plist_path`**: Массив адресов plist'ов, которые нужно изменить.


### write_executable_in_plists
```
fastlane write_executable_in_plists
```
Включение в plist'ах CFBundleExecutable для emcee

####Options

 * **`plist_path`**: Массив адресов plist'ов, которые нужно изменить.


### create_test_arg_json_for_ui_with_emcee
```
fastlane create_test_arg_json_for_ui_with_emcee
```
Создание test-arg-file.json для запуска UI тестов с Emcee

####Options

 * **`team`**: Название фиче-тимы, тесты которой будут запущены.

 * **`devices`**: Список девайсов, на которых будут запущены тесты в формате Девайс => Версия_оси.

 * **`app_bundle_path`**: Путь до файла приложения Мобильного банка.

 * **`runner_path`**: Путь до приложения раннера.

 * **`xctest_path`**: Путь до файла .xctest .

 * **`plugun_path`**: Путь до бинарника с плагином.

 * **`login`**: Логин учетной записи для авторизации в allure.

 * **`password`**: Пароль от учетной записи для авторизации в allure.

 * **`run_name`**: Название рана в allure.

 * **`xcode_version`**: Версия xcode.

 * **`allure_project_id`**: ID проекта в allure.tinkoff.ru

 * **`allure_result_path`**: Путь до json с данными после создания рана в allure

 * **`destination_path`**: путь до результирующего json

 * **`mobile_tools_url`**: url до репозитория mobile tools

 * **`repo_name`**: уникальное имя репозитория проекта для отправления в сервис

 * **`groups_count`**: Количество потоков, на которых будут запускаться тесты


### create_test_arg_json_for_unit_with_emcee
```
fastlane create_test_arg_json_for_unit_with_emcee
```
Создание test-arg-file.json для запуска юнитов Emcee

####Options

 * **`devices`**: Список девайсов, на которых будут запущены тесты в формате Девайс => Версия_оси.

 * **`app_bundle_path`**: Путь до файла приложения Мобильного банка.

 * **`runner_path`**: Путь до приложения раннера.

 * **`xctest_paths`**: Json c путями до файлов .xctest => массивом путей до файлов с тестами

 * **`plugun_path`**: Путь до бинарника с плагином.

 * **`teamcity_auth_token`**: Токен для пробрасывания в урлы с артефактами.

 * **`login`**: Логин учетной записи для авторизации в allure.

 * **`password`**: Пароль от учетной записи для авторизации в allure.

 * **`run_name`**: Название рана в allure.

 * **`xcode_version`**: Версия xcode.

 * **`allure_project_id`**: ID проекта в allure.tinkoff.ru

 * **`allure_result_path`**: Путь до json с данными после создания рана в allure

 * **`destination_path`**: путь до результирующего json

 * **`mobile_tools_url`**: url до репозитория mobile tools

 * **`schedule_strategy`**: стратегия распределения тестов

 * **`repo_name`**: уникальное имя репозитория проекта для отправления в сервис


### run_emcee
```
fastlane run_emcee
```
Запуск Emcee

####Options

 * **`queue_config_url`**: URL репозитория с конфигом очереди

 * **`tests_config_name`**: Название файла конфига с тестами

 * **`groups_count`**: Количество потоков, на которых будут запускаться тесты


### unzip_build_artifacts
```
fastlane unzip_build_artifacts
```

### update_ci_config
```
fastlane update_ci_config
```
Сгенерировать конфиг

####Options

 * **`number_of_runners`**: Количество раннеров


### create_distributed_tests_config
```
fastlane create_distributed_tests_config
```
Сгенерировать файл распределенных тестов

####Options

 * **`groups_count`**: Количество потоков, на которых будут запускаться тесты

 * **`team`**: Название фиче-тимы, тесты которой будут запущены.

 * **`repo_name`**: уникальное имя репозитория проекта для отправления в сервис


### create_allure_run
```
fastlane create_allure_run
```
Создать ран в Allure

####Options

 * **`token`**: Токен от allure для отправления туда результатов.

 * **`run_name`**: Название рана в allure. Необязательный параметр, по умолчанию используется Emcee run iOS

 * **`allure_project_id`**: Id проекта в allure. Необязательный параметр, по умолчанию используется 90


### run_prepared_ui_test_group
```
fastlane run_prepared_ui_test_group
```
Запуск тестов в параллельном режиме с ранжированнием по бакетам. Снапшоты исключены из прогона

Запускается на CI для ночного прогона всех тестов. Содержит ретраи упавших тестов.

####Options

 * **`group_index`**: Номер запускаемой группы

 * **`only_test_configurations`**: Список конфигов, с которыми будут запускаться тесты. По умолчанию используется ["Default"]

 * **`version`**: Версия iOS. Необязательный параметр, по умолчанию используется 14.5

 * **`model`**: Версия симулятора. Необязательный параметр, по умолчанию используется iPhone SE 2

 * **`skip`**: Список тестов, которые будут пропущены. Необязательный параметр, по умолчанию используется 

 * **`repo_name`**: уникальное имя репозитория проекта для отправления в сервис


### download_xctestsreportparser_binary
```
fastlane download_xctestsreportparser_binary
```
Подготовка XCTestsReportsParser

####Options

 * **`parser_url`**: URL бинарника с парсером


### deploy_qa_enterprise
```
fastlane deploy_qa_enterprise
```
Парсим JSON в поиске упавших тестов

Получение упавших тестов из JSON

Функция для получения полного пути до каталога с репортами.

Функция для выдачи пермишенов в MB.

Распределение тестов по группам

Выполнение запроса distribute для распределения сервисом тестов по группам

Парсинг .xcresult - формирование json

Отправление сервису данных после прогона тестов

Выполнение запроса receive для отправки данных сервису

Получение полного пути до каталога со скриптами (scripts)

Форматирование времени - hours-min-sec-ms из ms

Формирование и выполнение команды на отправление результатов в allure

Авторизация в allurectl

Отправление результатов в аллюр

Формирование строки с аргументами
### deploy_emcee_run_report
```
fastlane deploy_emcee_run_report
```

### deploy_qa_testflight
```
fastlane deploy_qa_testflight
```

### deploy_appstore
```
fastlane deploy_appstore
```

### upload_release_appstore_symbols
```
fastlane upload_release_appstore_symbols
```

### upload_release_qa_appstore_symbols
```
fastlane upload_release_qa_appstore_symbols
```

### compose_slack_notification_from_reports
```
fastlane compose_slack_notification_from_reports
```
Read report json files generated by other builds

Agragates result and send slack message

See JSON examles in `docs/` directory
### update_local_configs
```
fastlane update_local_configs
```


----

This README.md is auto-generated and will be re-generated every time [_fastlane_](https://fastlane.tools) is run.
More information about fastlane can be found on [fastlane.tools](https://fastlane.tools).
The documentation of fastlane can be found on [docs.fastlane.tools](https://docs.fastlane.tools).
