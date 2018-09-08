---
title: Служебная программа клиента служб данных WCF (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 7c9b713571cea3d2c8c5f6511f2cfab7e87b80ee
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44189281"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>Служебная программа клиента служб данных WCF (DataSvcUtil.exe)

DataSvcUtil.exe представляет собой программу командной строки, предоставляемые службами данных WCF, который использует [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канала и формирующую клиентские классы службы данных, которые необходимы для доступа к службе данных из клиентского приложения .NET Framework. Эта программа формирует классы данных с использованием следующих источников метаданных.

-   Корневой URI службы данных. Эта программа запрашивает документ метаданных службы, в котором описывается модель данных, предоставленная службой данных. Дополнительные сведения см. в разделе [OData: документ метаданных службы](https://go.microsoft.com/fwlink/?LinkId=186070).

-   Файл модели данных (с расширением CSDL), определенный с помощью языка определения концептуальной схемы (CSDL), описанного в [ \[MC-CSDL\]: формат файла определения концептуальной схемы](https://go.microsoft.com/fwlink/?LinkID=159072) спецификации.

-   Файл EDMX, созданный при помощи программ для работы с моделью EDM, входящих в комплект Entity Framework. Дополнительные сведения см. в разделе [ \[MC-EDMX\]: модели EDM для формата упаковки служб данных](https://go.microsoft.com/fwlink/?LinkID=178833) спецификации.

Дополнительные сведения см. в разделе [как: вручную сформировать клиентские классы службы данных](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).

Программа DataSvcUtil.exe установлена в каталоге [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Во многих случаях этот файл находится в *C:\Windows\Microsoft.NET\Framework\v4.0*. Для 64-разрядных системах она находится в *C:\Windows\Microsoft.NET\Framework64\v4.0*. Также можно открыть средство DataSvcUtil.exe из командной строки разработчика для Visual Studio.

## <a name="syntax"></a>Синтаксис

```
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|------------|-----------------|
|`/dataservicecollection`|Указывает, что будет также сформирован код, необходимый для привязки объектов к элементам управления.|
|`/help`<br /><br /> -или-<br /><br /> `/?`|Отображает синтаксис команд и параметров программы.|
|`/in:` *\<Файл >*|Указывает файл CSDL или EDMX либо каталог, в котором находится этот файл.|
|`/language:`[VB&#124;c#]|Задает язык для сформированных файлов с исходным кодом. Язык по умолчанию — C#.|
|`/nologo`|Отключает вывод сообщения об авторских правах.|
|`/out:` *\<Файл >*|Задает имя файла с исходным кодом, в котором содержатся сформированные клиентские классы службы данных.|
|`/uri:` *\<строка >*|URI веб-канала OData.|
|`/version:`[1.0&#124;2.0]|Задает наибольшую принимаемую версию OData. Версия определяется на основе `DataServiceVersion` атрибут элемента DataService в возвращаемых метаданных службы данных. Дополнительные сведения см. в разделе [управление версиями службы данных](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md). При указании `/dataservicecollection` параметр, необходимо также указать `/version:2.0` для обеспечения привязки данных.|

## <a name="see-also"></a>См. также

- [Создание библиотеки клиентов службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [Практическое руководство. Добавление ссылки на службу данных](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
