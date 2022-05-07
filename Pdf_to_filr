import os
import pdfkit

'''for correct job this program:
pip install pdfkit
install wkhtmltopdf https://wkhtmltopdf.org/'''

# Сonfigure pdfkit to point to our installation of wkhtmltopdf
config = pdfkit.configuration(wkhtmltopdf=r"C:\Program Files\wkhtmltopdf\bin\wkhtmltopdf.exe")

download_page = input('Вставьте ссылку на страницу: ').strip()
name_of_file = input('Введите название файла: ').strip() + '.pdf'

# Checking that data has been entered
while download_page == '' or name_of_file == '':
    print('Неверная ссылка или имя файла')
    download_page = input('Вставьте ссылку на страницу: ')
    name_of_file = input('Введите название файла: ')

# If the page address is entered incorrectly or the page is not available
try:
    pdfkit.from_url(download_page, output_path=name_of_file, configuration=config)
except OSError:
    print('Запрошенная страница не найдена')

print(f'Файл с именем {name_of_file} создан\nОткрыть файл?')
q = input('Да / Нет: ')

if q == 'Да':
    path = name_of_file
    os.system(path)
else:
    print('Файл сохранен в рабочей папке программы')

