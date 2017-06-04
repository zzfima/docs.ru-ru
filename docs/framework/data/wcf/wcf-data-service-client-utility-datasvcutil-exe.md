---
title: "Клиентская программа служб WCF Data Services (DataSvcUtil.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Службы WCF Data Services, клиентская библиотека"
  - "Службы WCF Data Services, использование"
  - "Службы WCF Data Services, формирование классов клиентских данных"
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Клиентская программа служб WCF Data Services (DataSvcUtil.exe)
DataSvcUtil.exe представляет собой программу командной строки, предоставляемую службами [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], использующую канал [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] и формирующую клиентские классы службы данных, необходимые для доступа к службе данных из клиентского приложения .NET Framework.  Эта программа формирует классы данных с использованием следующих источников метаданных.  
  
-   Корневой URI службы данных.  Эта программа запрашивает документ метаданных службы, в котором описывается модель данных, предоставленная службой данных.  Дополнительные сведения см. в разделе [OData: документ метаданных службы](http://go.microsoft.com/fwlink/?LinkId=186070).  
  
-   Файл модели данных \(CSDL\), определенный с помощью языка определения концептуальной схемы \(CSDL\), описанного в спецификации [\[MC\-CSDL\]: формат файла определения концептуальной схемы](http://go.microsoft.com/fwlink/?LinkID=159072).  
  
-   Файл EDMX, созданный при помощи программ для работы с моделью EDM, входящих в комплект Entity Framework.  Дополнительные сведения см. в спецификации [\[MC\-EDMX\]: модели EDM для формата упаковки служб данных](http://go.microsoft.com/fwlink/?LinkID=178833).  
  
 Для получения дополнительной информации см. [Как формировать клиентские классы службы данных вручную](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
 Программа DataSvcUtil.exe установлена в каталоге [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  Обычно это папка C:\\Windows\\Microsoft.NET\\Framework\\v4.0.  Для 64\-разрядных версий систем это папка C:\\Windows\\Microsoft.NET\\Framework64\\v4.0.  Доступ к программе DataSvcUtil.exe можно также получить из командной строки Visual Studio \(щелкните **Пуск**, последовательно укажите **Все программы**, **Microsoft Visual Studio 2010**, **Средства Visual Studio**, а затем щелкните **Командная строка Visual Studio 2010**\).  
  
## Синтаксис  
  
```  
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`/dataservicecollection`|Указывает, что будет также сформирован код, необходимый для привязки объектов к элементам управления.|  
|`/help`<br /><br /> \-или\-<br /><br /> `/?`|Отображает синтаксис команд и параметров программы.|  
|`/in:` *\<файл\>*|Указывает файл CSDL или EDMX либо каталог, в котором находится этот файл.|  
|`/language:`\[VB&#124;CSharp\]|Задает язык для сформированных файлов с исходным кодом.  Язык по умолчанию — C\#.|  
|`/nologo`|Отключает вывод сообщения об авторских правах.|  
|`/out:` *\<файл\>*|Задает имя файла с исходным кодом, в котором содержатся сформированные клиентские классы службы данных.|  
|`/uri:` *\<string\>*|Универсальный код ресурса \(URI\) канала [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].|  
|`/version:`\[1.0&#124;2.0\]|Задает максимально принимаемую версию [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  Эта версия определяется на основе атрибута `DataServiceVersion` элемента DataService в возвращаемых метаданных службы данных.  Для получения дополнительной информации см. [Управление версиями данных](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  Если указан параметр `/dataservicecollection`, необходимо также задать параметр `/version:2.0`, чтобы включить привязку данных.|  
  
## См. также  
 [Формирование клиентской библиотеки службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)   
 [Как добавить ссылку на службу данных](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)