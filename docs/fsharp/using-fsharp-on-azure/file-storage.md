---
title: Начало работы с хранилищем файлов Azure с использованиемF#
description: Store файла данных в облаке с хранилищем файлов Azure и подключить к общей облачной папке из виртуальной машины Azure (ВМ) или из локального приложения под управлением Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fa6dadc863bb9116cfac5afd7cd22a724bc7afe2
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969600"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Начало работы с хранилищем файлов Azure с помощью языка F\#

Хранилище файлов Azure — это служба, предоставляющая файловые ресурсы в облаке, используя стандартные [протокол Server Message Block (SMB)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx). Поддерживаются протоколы SMB 2.1 и SMB 3.0. С хранилищем файлов Azure можно переносить устаревшие приложения, использующие файловые ресурсы Azure быстро и без дорогостоящей перезаписи. Приложения, работающие на виртуальных машинах Azure или облачных службах или из локальных клиентов можно подключить файловый ресурс в облаке, так же, как настольное приложение подключает обычную общую папку SMB. Любое количество компонентов приложений можно подключать и одновременно получить доступ к общей папки хранилища.

Общие сведения о хранилище файлов, см. в разделе [руководство по .NET для хранилища файлов](/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Предварительные требования

Чтобы использовать это руководство, необходимо сначала [создать учетную запись хранения](/azure/storage/storage-create-storage-account).
Вам также потребуется ключ доступа к хранилищу для этой учетной записи.

## <a name="create-an-f-script-and-start-f-interactive"></a>Создание F# сценариев и запустить F# интерактивный

Примеры в этой статье можно использовать в любом F# приложения или F# скрипта. Чтобы создать F# скрипт, создайте файл с `.fsx` расширение, например `files.fsx`в вашей F# среды разработки.

Затем используйте [диспетчера пакетов](package-management.md) например [Paket](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) для установки `WindowsAzure.Storage` пакета и ссылка `WindowsAzure.Storage.dll` в скрипте, с помощью `#r`директива.

### <a name="add-namespace-declarations"></a>Добавьте объявления пространств имен

Добавьте следующий `open` операторы в верхнюю часть `files.fsx` файла:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Получить строку подключения

В этом руководстве вам потребуется строки подключения к службе хранилища Azure. Дополнительные сведения о строках подключения см. в разделе [Настройка строк подключения службы хранилища](/azure/storage/storage-configure-connection-string).

Для этого руководства вы введете строку подключения в скрипте, следующим образом:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Однако это **не рекомендуется** реальных проектов. Ключ учетной записи хранения похож на корневой пароль для учетной записи хранения. Не забудьте защитить ключ учетной записи хранения. Избегайте распределения его другим пользователям, в коде, или сохранить его в текстовом файле, доступном другим пользователям. Можно повторно создать ключ с помощью портала Azure, если вы считаете, что он мог быть скомпрометирован.

Для реальных приложений, чтобы сохранить строку подключения хранилища рекомендуется в файле конфигурации. Чтобы получить строку подключения из файла конфигурации, это можно сделать:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Использование диспетчера конфигураций Azure не является обязательным. Можно также использовать API, например .NET Framework `ConfigurationManager` типа.

### <a name="parse-the-connection-string"></a>Проанализировать строку подключения

Чтобы проанализировать строку подключения, используйте следующую команду:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Эта команда возвращает `CloudStorageAccount`.

### <a name="create-the-file-service-client"></a>Создание клиента службы файлов

`CloudFileClient` Типа позволяет программно использовать файлы, хранящиеся в хранилище файлов. Вот один из способов создания клиента службы:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Теперь вы готовы написать код, который считывает и записывает данные в хранилище файлов.

## <a name="create-a-file-share"></a>Создание общей папки

В этом примере показано, как создать файловый ресурс в том случае, если он еще не существует:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Создание корневого каталога и подкаталога

Здесь вы получаете корневой каталог и получите вложенный каталог корневого элемента. Можно создать, и если они еще не существуют.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Загрузить текст в формате

В этом примере показано, как загрузить текст в формате.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Загрузите файл локальную копию файла

Здесь необходимо скачать файл, который только что создали, добавив содержимое в локальном файле.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Установить максимальный размер для общей папки

В приведенном ниже примере показано, как проверить текущее использование для общей папки и как задать квоту для общей папки. `FetchAttributes` для заполнения общего ресурса необходимо вызвать `Properties`, и `SetProperties` для распространения локальных изменений в хранилище файлов Azure.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Создание подписи общего доступа для файла или общей папки

Вы можете создать подпись общего доступа (SAS) для общей папки или отдельного файла. Можно также создать политики общего доступа в общей папке, чтобы управлять подписями общего доступа. Создание политики общего доступа рекомендуется, так как она позволяет отменить SAS, если она скомпрометирована.

Здесь создается общий доступ к политике в общей папке, а затем использовать эту политику для обеспечения ограничения SAS для файла в общей папке.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Дополнительные сведения о создании и использовании подписей общего доступа см. в разделе [использование подписи доступа (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) и [Создание и использование SAS с помощью хранилища BLOB-объектов](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Копирование файлов

Файл можно скопировать в другой файл или большой двоичный объект или большой двоичный объект в файл. При копировании большого двоичного объекта в файл или файл в большой двоичный объект, вы *необходимо* использовать подпись общего доступа (SAS) для проверки подлинности исходного объекта, даже если копирование производится внутри одной учетной записи.

### <a name="copy-a-file-to-another-file"></a>Скопируйте файл в другой файл

Здесь можно скопировать файл в другой файл в той же общей папке. Так как эта операция копирования осуществляет копирование между файлами в одну и ту же учетную запись хранения, можно использовать проверку подлинности Shared Key для выполнения копирования.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Скопируйте файл в большой двоичный объект

Здесь, создайте файл и скопируйте его в большой двоичный объект в учетной записи хранения. Можно создать подписанный URL-адрес для исходного файла, который используется службой для проверки подлинности доступа к исходному файлу во время операции копирования.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Таким же образом можно скопировать большой двоичный объект в файл. Если исходный объект является большой двоичный объект, создайте SAS для аутентификации доступа к этого большого двоичного объекта во время операции копирования.

## <a name="troubleshooting-file-storage-using-metrics"></a>Устранение неполадок хранилища файлов с помощью метрик

Аналитика службы хранилища Azure поддерживает метрики для хранилища файлов. С данными метрик можно отслеживать запросы и диагностировать проблемы.

Вы можете включить метрики для хранилища файлов из [портал Azure](https://portal.azure.com), или это можно сделать из F# следующим образом:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Следующие шаги

Найти по следующим ссылкам, Дополнительные сведения о хранилище файлов Azure.

### <a name="conceptual-articles-and-videos"></a>Тематические статьи и видео

- [Хранилище файлов Azure: удобная облачная файловая система SMB для Windows и Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Как использовать хранилище файлов Azure с Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Поддержка средств для хранилища файлов

- [С помощью Azure PowerShell со службой хранилища Azure](/azure/storage/storage-powershell-guide-full)
- [Как использовать AzCopy со службой хранилища Microsoft Azure](/azure/storage/storage-use-azcopy)
- [С помощью Azure CLI со службой хранилища Azure](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Ссылка

- [Клиентская библиотека хранилища для .NET](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Справочник по API REST службы файлов](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Сообщения в блогах

- [Хранилище файлов Azure теперь общедоступна](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Хранилище внутри файлов Azure](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [Введение в службы файлов Microsoft Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [Сохраняемые подключения к файлам Microsoft Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
