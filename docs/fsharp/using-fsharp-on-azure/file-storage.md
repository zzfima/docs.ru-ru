---
title: "Начало работы с хранилищем файлов Azure, с помощью F #"
description: "Хранить файл данных в облаке с хранилищем файлов Azure и подключения к общей папке облака на основе Azure виртуальной машины (VM) или из локального приложения под управлением Windows."
keywords: "Visual f #, f #, функционального программирования, .NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5c26a0aa-186e-476c-9f87-e0191754579e
ms.openlocfilehash: 66b2503744e9024deac3d6dabea57da4fd393bd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Начало работы с хранилищем файлов Azure, с помощью F # #

Хранилище Azure файл — это служба, предоставляющая файловыми ресурсами общего доступа в облаке с использованием стандарта [протокола Server Message Block (SMB)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx). Поддерживаются SMB 2.1 и SMB 3.0. При хранении файлов Azure можно перенести старых приложений, использующих общим файловым ресурсам в Azure, быстро и без дорогостоящей излишнего копирования. Приложения, работающие в Azure виртуальные машины или облачные службы или от локальных клиентов можно подключить общую папку в облаке, так же, как настольного приложения подключает обычной общей папки SMB. Любое количество компонентов приложения можно подключить и одновременно получить доступ к общей папки хранилища.

Концептуальный обзор хранилища файлов, см. в разделе [руководство по .NET для хранения файлов](/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Предварительные требования

Чтобы использовать это руководство, необходимо сначала [создать учетную запись хранилища Azure](/azure/storage/storage-create-storage-account).
Кроме того, потребуется ключ доступа хранилища для этой учетной записи.

## <a name="create-an-f-script-and-start-f-interactive"></a>Создание скрипта F # и начала F #, интерактивный

Примеры в этой статье используется в F # приложения или скрипта F #. Чтобы создать скрипт F #, создайте файл с `.fsx` расширение, например `files.fsx`, в среде разработки F #.

Затем используйте [диспетчера пакетов](package-management.md) такие как [Paket](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) установка `WindowsAzure.Storage` пакета и ссылка `WindowsAzure.Storage.dll` в скрипте с помощью `#r`директивы.

### <a name="add-namespace-declarations"></a>Добавьте объявления пространств имен

Добавьте следующие `open` инструкции в начало `files.fsx` файла:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Получение строки подключения

Для этого учебника потребуется строку подключения хранилища Azure. Дополнительные сведения о строках соединения см. в разделе [Настройка строки подключения хранилища](/azure/storage/storage-configure-connection-string).

Учебник вы введете строки подключения в скрипте, следующим образом:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Однако это **не рекомендуется** для реальных проектах. Ключ учетной записи хранилища аналогична корневой пароль для учетной записи хранилища. Всегда будьте внимательны защитить ключ учетной записи хранилища. Избегайте распространением их другим пользователям, жестко запрограммированные ее или сохранить в текстовый файл, доступный другим пользователям. Можно повторно создать ключ с помощью портала Azure, если вы считаете, что он был скомпрометирован.

Для реальных приложений для сохранения строки подключения хранилища рекомендуется в файле конфигурации. Чтобы получить строку подключения из файла конфигурации, это можно сделать:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

С помощью диспетчера конфигурации Azure является необязательным. Можно также использовать интерфейс API, например .NET Framework `ConfigurationManager` типа.

### <a name="parse-the-connection-string"></a>Синтаксический анализ строки соединения

Чтобы обработать строку подключения, используйте:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Будет возвращен `CloudStorageAccount`.

### <a name="create-the-file-service-client"></a>Создание клиента службы файлов

`CloudFileClient` Тип позволяет программно использовать файлы, хранящиеся в хранилище файлов. Вот один из способов создания клиента службы.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Теперь вы готовы написать код, который считывает и записывает данные в хранилище файлов.

## <a name="create-a-file-share"></a>Создание общей папки

В этом примере показано, как создать общую папку, если он еще не существует:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Создать корневой каталог и подкаталог

Здесь, вы получаете корневой каталог и получить вложенный каталог к корневому каталогу. Как создать, если они еще не существуют.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Загрузить текст в формате

В этом примере показано, как загрузить текст в формате.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Загрузите файл локальную копию файла

Здесь вы загрузите файл только что создали, добавления содержимого в локальный файл.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Установить максимальный размер для общей папки

В приведенном ниже примере показано, как проверить текущее использование для общей папки и как задать квоту для общей папки. `FetchAttributes`необходимо вызвать, чтобы заполнить общую папку `Properties`, и `SetProperties` переносить локальные изменения в хранилище файлов Azure.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Создать подпись общего доступа для файла или общей папки

Вы можете создать подписанный URL-адрес (SAS) для общей папки или отдельного файла. Можно также создать политики общего доступа на файловом ресурсе, чтобы управлять подписями общего доступа. Создание политики общего доступа рекомендуется, так как она предоставляет средства отзыва SAS, если он должен быть скомпрометирован.

Здесь, можно создать общий доступ к политике в общей папке, а затем использовать эту политику для обеспечения ограничения SAS на файл в общей папке.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Дополнительные сведения о создании и использовании подписанных URL-адресов см. в разделе [с помощью подписи URL (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) и [Создание и использование SAS с хранилищем больших двоичных объектов](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Копирование файлов

Файл можно скопировать в другой файл или большой двоичный объект или большого двоичного объекта в файл. При копировании большого двоичного объекта в файл или файл в большой двоичный объект можно *должен* использовать подписанный URL-адрес (SAS) для проверки подлинности исходного объекта, даже при копировании данных в одну и ту же учетную запись хранилища.

### <a name="copy-a-file-to-another-file"></a>Скопируйте файл в другой файл

Здесь можно скопировать файл на другой файл в ту же папку. Поскольку эта операция копирования копирует между файлами в учетную запись хранения, можно использовать проверку подлинности Shared Key для выполнения копирования.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Скопируйте файл в большой двоичный объект

Здесь, создайте файл и скопируйте его в большой двоичный объект в одну и ту же учетную запись хранилища. Можно создать SAS для исходного файла, который используется службой для проверки подлинности доступа к файлу исходного кода во время операции копирования.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Таким же образом, можно скопировать большого двоичного объекта в файл. Если исходный объект является большой двоичный объект, необходимо создайте SAS для проверки подлинности доступа к этим большим двоичным объектом во время операции копирования.

## <a name="troubleshooting-file-storage-using-metrics"></a>Устранение неполадок с помощью метрик хранилища файлов

Аналитика хранилища Azure поддерживает метрики для хранения файлов. С данными метрик можно отслеживать запросы и диагностировать проблемы.

Можно включить метрики для хранения файлов из [портала Azure](https://portal.azure.com), или это можно сделать из F # следующим образом:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Следующие шаги

См. Дополнительные сведения о хранилище файлов Azure эти ссылки.

### <a name="conceptual-articles-and-videos"></a>Основные статьи и видео

- [Хранилище файлов Azure: издержками облака SMB файловой системы для Windows и Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Использование хранилища Azure файла с Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Инструменты для хранения файлов

- [С помощью Azure PowerShell с помощью хранилища Azure](/azure/storage/storage-powershell-guide-full)
- [Как использовать AzCopy с хранилищем Microsoft Azure](/azure/storage/storage-use-azcopy)
- [С помощью Azure CLI с помощью хранилища Azure](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Ссылка

- [Клиентская библиотека хранилища для Справочник по .NET](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Справочник по API REST службы файлов](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Сообщения в блогах

- [Хранилище файлов Azure теперь стал общедоступным](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Хранение файлов в Azure](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [Знакомство с приложением службы файлов Microsoft Azure](http://blogs.msdn.com/b/windowsazurestorage/archive/2014/05/12/introducing-microsoft-azure-file-service.aspx)
- [Сохранение подключения к Microsoft Azure](http://blogs.msdn.com/b/windowsazurestorage/archive/2014/05/27/persisting-connections-to-microsoft-azure-files.aspx)
