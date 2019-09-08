---
title: Служебная программа клиента служб данных WCF (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 97e9502176e0cc2f36d67ee3dc8e8d0739a009b2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790191"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>Служебная программа клиента служб данных WCF (DataSvcUtil.exe)

DataSvcUtil. exe — это средство командной строки, предоставляемое WCF Data Services, которое использует [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канал и создает клиентские классы службы данных, необходимые для доступа к службе данных из клиентского приложения .NET Framework. Эта программа формирует классы данных с использованием следующих источников метаданных.

- Корневой URI службы данных. Эта программа запрашивает документ метаданных службы, в котором описывается модель данных, предоставленная службой данных. Дополнительные сведения см. в [разделе OData: Документ](https://go.microsoft.com/fwlink/?LinkId=186070)метаданных службы.

- Файл модели данных (CSDL), определенный на [ \[языке CSDL, в соответствии с определением MC-CSDL\]: Спецификация формата](https://go.microsoft.com/fwlink/?LinkID=159072) файла определения концептуальной схемы.

- Файл EDMX, созданный при помощи программ для работы с моделью EDM, входящих в комплект Entity Framework. Дополнительные сведения см. на [ \[странице MC-EDMX\]: EDM спецификации формата](https://go.microsoft.com/fwlink/?LinkID=178833) упаковки служб данных.

Дополнительные сведения см. в разделе [Как Создание классов](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)клиентской службы данных вручную.

Средство DataSvcUtil. exe устанавливается в каталог .NET Framework. Во многих случаях это находится в *C:\Windows\Microsoft.NET\Framework\v4.0*. Для 64-разрядных систем это расположение находится в *C:\Windows\Microsoft.NET\Framework64\v4.0*. Вы также можете получить доступ к средству DataSvcUtil. exe из Командная строка разработчика для Visual Studio.

## <a name="syntax"></a>Синтаксис

```
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a>Параметры

|Параметр|Описание|
|------------|-----------------|
|`/dataservicecollection`|Указывает, что будет также сформирован код, необходимый для привязки объектов к элементам управления.|
|`/help`<br /><br /> -или-<br /><br /> `/?`|Отображает синтаксис команд и параметров программы.|
|`/in:` *>\<файлов*|Указывает файл CSDL или EDMX либо каталог, в котором находится этот файл.|
|`/language:`[VB&#124;CSharp]|Задает язык для сформированных файлов с исходным кодом. Язык по умолчанию — C#.|
|`/nologo`|Отключает вывод сообщения об авторских правах.|
|`/out:` *>\<файлов*|Задает имя файла с исходным кодом, в котором содержатся сформированные клиентские классы службы данных.|
|`/uri:` *строка\<>*|URI веб-канала OData.|
|`/version:`[1.0&#124;2.0]|Указывает максимально допустимую версию OData. Версия определяется на основе `DataServiceVersion` атрибута элемента данных в возвращенных метаданных службы данных. Дополнительные сведения см. в разделе [Управление версиями службы данных](data-service-versioning-wcf-data-services.md). При указании `/dataservicecollection` параметра необходимо также указать `/version:2.0` , чтобы включить привязку данных.|

## <a name="see-also"></a>См. также

- [Создание библиотеки клиентов службы данных](generating-the-data-service-client-library-wcf-data-services.md)
- [Практическое руководство. Добавить ссылку на службу данных](how-to-add-a-data-service-reference-wcf-data-services.md)
