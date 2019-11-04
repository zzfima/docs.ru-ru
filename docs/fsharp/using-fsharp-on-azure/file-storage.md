---
title: Начало работы с хранилищем файлов Azure с помощью языка F#
description: Храните данные файлов в облаке с помощью хранилища файлов Azure и подключите облачный файловый ресурс из виртуальной машины Azure или из локального приложения под управлением Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 9c25ab930abcbe7b358ae63c709aba4e97aed3be
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423865"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Начало работы с хранилищем файлов Azure с помощью F\#

Хранилище файлов Azure — это служба, которая предлагает общие файловые ресурсы в облаке с помощью стандартного [протокола SMB](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx). Поддерживаются SMB 2,1 и SMB 3,0. С помощью хранилища файлов Azure можно быстро перенести устаревшие приложения, использующие общие файловые ресурсы, в Azure и без дорогостоящей перезаписи. Приложения, работающие на виртуальных машинах или облачных службах Azure или локальных клиентах, могут подключать общую папку в облаке, так же как настольные приложения подключаются к типичному общему ресурсу SMB. После этого любое количество компонентов приложения может одновременно подключаться и обращаться к общей папке хранилища файлов.

Общие сведения о хранилище файлов см. [в этом](/azure/storage/storage-dotnet-how-to-use-files)разделе.

## <a name="prerequisites"></a>Необходимые компоненты

Для работы с этим руководством необходимо сначала [создать учетную запись хранения Azure](/azure/storage/storage-create-storage-account).
Вам также потребуется ключ доступа к хранилищу для этой учетной записи.

## <a name="create-an-f-script-and-start-f-interactive"></a>Создание F# скрипта и запуск F# интерактивного

Примеры в этой статье можно использовать как в F# приложении, так и в F# сценарии. Чтобы создать F# скрипт, создайте файл с расширением `.fsx`, например `files.fsx`, в среде F# разработки.

Затем используйте [Диспетчер пакетов](package-management.md) , например [пакет](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) , для установки пакета `WindowsAzure.Storage` и ссылку `WindowsAzure.Storage.dll` в скрипте с помощью директивы `#r`.

### <a name="add-namespace-declarations"></a>Добавить объявления пространств имен

Добавьте следующие `open` операторы в начало файла `files.fsx`:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Получение строки подключения

Для работы с этим руководством вам потребуется строка подключения к службе хранилища Azure. Дополнительные сведения о строках подключения см. в разделе [Настройка строк подключения к хранилищу](/azure/storage/storage-configure-connection-string).

В этом руководстве вы введете строку подключения в сценарий следующим образом:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Однако это **не рекомендуется** для реальных проектов. Ключ учетной записи хранения аналогичен корневому паролю для вашей учетной записи хранения. Всегда будьте внимательны, чтобы защитить ключ учетной записи хранения. Не рекомендуется распространять его другим пользователям, жестко программировать или сохранять в виде обычного текстового файла, доступного для других пользователей. Вы можете повторно создать ключ с помощью портала Azure, если считаете, что он был скомпрометирован.

Для реальных приложений лучшим способом поддержания строки подключения к хранилищу является файл конфигурации. Чтобы получить строку подключения из файла конфигурации, можно сделать следующее:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Использование Configuration Manager Azure является необязательным. Вы также можете использовать API, например тип .NET Framework `ConfigurationManager`.

### <a name="parse-the-connection-string"></a>Анализ строки подключения

Чтобы проанализировать строку подключения, используйте:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Это приведет к возврату `CloudStorageAccount`.

### <a name="create-the-file-service-client"></a>Создание клиента службы файлов

Тип `CloudFileClient` позволяет программно использовать файлы, хранящиеся в хранилище файлов. Вот один из способов создания клиента службы:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Теперь все готово для написания кода, считывающего данные из хранилища файлов и записывающего их в хранилище.

## <a name="create-a-file-share"></a>Создание общей папки

В этом примере показано, как создать файловый ресурс, если он еще не существует:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Создание корневого каталога и подкаталога

Здесь вы получаете корневой каталог и подкаталогом корневого каталога. Они создаются, если они еще не существуют.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Отправка текста в виде файла

В этом примере показано, как передать текст в виде файла.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Скачать файл в локальную копию файла

Здесь вы скачиваете только что созданный файл, добавляя содержимое в локальный файл.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Установка максимального размера для общей папки

В приведенном ниже примере показано, как проверить текущее использование общего ресурса и задать квоту для общей папки. для заполнения `Properties`общего ресурса необходимо вызвать `FetchAttributes` и `SetProperties` распространить локальные изменения в хранилище файлов Azure.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Создание подписи общего доступа для файла или файлового ресурса

Вы можете создать подписанный URL-адрес (SAS) для общей папки или отдельного файла. Кроме того, можно создать политику общего доступа в общей папке для управления подписанными URL-доступом. Рекомендуется создать политику общего доступа, так как она предоставляет средства отмены SAS, если она должна быть скомпрометирована.

Здесь вы создаете политику общего доступа для общей папки, а затем используете эту политику для предоставления ограничений для SAS для файла в общей папке.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Дополнительные сведения о создании и использовании подписанных URL-адресов см. в статьях [Использование подписей общего доступа (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) и [Создание и использование SAS с хранилищем BLOB-объектов](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Копирование файлов

Файл можно скопировать в другой файл или в большой двоичный объект или в большой двоичный объект в файл. Если вы копируете большой двоичный объект в файл или файл в большой двоичный объект, *необходимо* использовать подписанный URL-адрес (SAS) для проверки подлинности исходного объекта, даже если вы копируете его в ту же учетную запись хранения.

### <a name="copy-a-file-to-another-file"></a>Копирование файла в другой файл

Здесь вы копируете файл в другой файл в той же общей папке. Так как эта операция копирования копирует между файлами в одной учетной записи хранения, для копирования можно использовать проверку подлинности с помощью общего ключа.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Копирование файла в большой двоичный объект

Здесь вы создаете файл и копируете его в большой двоичный объект в той же учетной записи хранения. Создайте SAS для исходного файла, который служба использует для проверки подлинности доступа к исходному файлу во время операции копирования.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Вы можете скопировать большой двоичный объект в файл таким же образом. Если исходный объект является BLOB-объектом, создайте SAS для проверки подлинности доступа к этому большому двоичному объекту во время операции копирования.

## <a name="troubleshooting-file-storage-using-metrics"></a>Устранение неполадок хранилища файлов с помощью метрик

Аналитика Службы хранилища Azure поддерживает метрики для хранилища файлов. С помощью данных метрик можно отслеживать запросы и диагностировать проблемы.

Вы можете включить метрики для хранилища файлов на [портале Azure](https://portal.azure.com). также можно сделать это F# следующим образом:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Следующие шаги

Дополнительные сведения о хранилище файлов Azure см. в этих ссылках.

### <a name="conceptual-articles-and-videos"></a>Концептуальные статьи и видеоматериалы

- [Хранилище файлов Azure. облачная файловая система SMB для Windows и Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Использование хранилища файлов Azure с Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Поддержка инструментария для хранилища файлов

- [Использование Azure PowerShell с хранилищем Azure](/azure/storage/storage-powershell-guide-full)
- [Использование AzCopy с служба хранилища Microsoft Azure](/azure/storage/storage-use-azcopy)
- [Использование Azure CLI с хранилищем Azure](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Справочники

- [Справочник по клиентской библиотеке хранилища для .NET](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Справочник по REST API службы файлов](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Записи блога

- [Хранилище файлов Azure теперь общедоступно](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Внутреннее хранилище файлов Azure](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [Введение в Microsoft Azure файловую службу](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [Сохранение соединений с файлами Microsoft Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
