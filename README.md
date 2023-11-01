## Учебные материалы по упаковке приложений на Python. 
### Развертывание на локальной машине:
#### Mac OS, Linux OS
1. Создаем виртуальное окружение:
   ```bash
   python -m venv venv
   ```
   (или python3, если в системе стоит несколько интерпретаторов)
   ```bash
   python3 -m venv venv
   ```
2. Активируем venv: 
   ```bash
   source venv/bin/activate
   ```
3. Устанавливаем зависимости (необязательный шаг, т.к. зависимостей нет): 
   ```bash
   pip install -r requirements.txt 
   ```
   (или pip3 если стоит несколько интерпретаторов)
   ```bash
   pip3 install -r requirements.txt
   ```
4. Для деактивации виртуального окружения наберите команду 
   ```bash
   deactivate
   ```
#### Windows OS
1. Создаем виртуальное окружение: 
   ```bash
   python -m venv venv
   ``` 
   (или python3, если в системе стоит несколько интерпретаторов)
   ```bash
   python3 -m venv venv
   ```
2. Активируем venv: 
   ```bash
   venv\scripts\activate
   ```
   Если вы используете PowerShell и при активации виртуального окружения вы получаете ошибку с указанием на невозможность запуска скрипта,
то необходимо изменить политики запуска скриптов. Для этого запустите PowerShell от имени администратора и
наберите команду: 
   ```bash
   Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope LocalMachine
   ``` 
   Эта команда установит политику запуска только подписанных скриптов для всех локальных пользователей. При дальнейшей активации
виртуального окружения нужно будет указать запускать скрипт всегда, набрав А.
3. Устанавливаем зависимости (необязательный шаг, т.к. зависимостей нет): 
   ```bash
   pip install -r requirements.txt
   ```
   (или pip3 если стоит несколько интерпретаторов)
   ```bash
   pip3 install -r requirements.txt 
   ```
4. Для деактивации виртуального окружения наберите команду 
   ```bash
   deactivate
   ```
5. Сборка дистрибутива
   ```bash
   pyinstaller --windowed --name "hello-world" --icon icon.ico app.py
   ```

   --windowed под macOS обязателен, под Linux данный параметр не имеет эффекта.
   Данный параметр скрывает окно терминала при работе приложения.
   
   --name указывает на необходимость принять пользовательское имя файла и папки дистрибутива,
   указанное в кавычках
   
   --icon указывает имя файла иконки (icon.ico) для использования в качестве иконки для исполняемого файла

   Также сборку дистрибутива можно выполнить при помощи файла конфигурации сборки app.spec
   ```bash
   pyinstaller app.spec
   ```
   
   