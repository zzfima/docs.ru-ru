---
title: "Генератор модели EDM (EdmGen.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe8297a1-1fc3-48ce-8eeb-f70f63f857aa
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: aea41a58697acaad0b089f8e35b9f870e8bf841d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="edm-generator-edmgenexe"></a>Генератор модели EDM (EdmGen.exe)
EdmGen.exe - программа командной строки, предназначенная для работы с файлами моделей и сопоставлениями [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Средство EdmGen.exe применяется для следующих целей.  
  
-   Соединения с источником данных с помощью определяемого источником данных поставщика данных .NET Framework, а также формирования файлов концептуальной модели (CSDL), модели хранения (SSDL) и сопоставления (MSL), используемых платформой [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Дополнительные сведения см. в разделе [как: использование EdmGen.exe для создания модели и сопоставления файлов](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
-   проверки существующей модели Дополнительные сведения см. в разделе [как: использование EdmGen.exe для проверки модели и сопоставления файлов](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md).  
  
-   Создания файла кода C# или Visual Basic, который содержит классы объектов, сформированные из файла концептуальной модели (CSDL). Дополнительные сведения см. в разделе [как: использование EdmGen.exe для создания кода объектного уровня](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md).  
  
-   Создания файла кода C# или Visual Basic, который содержит заранее сформированные представления для существующей модели. Для получения дополнительной информации [как: Pre-Generate представления для повышения производительности запросов](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579).  
  
 Средство EdmGen.exe устанавливается в каталог [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]. Чаще всего она находится в папке C:\windows\Microsoft.NET\Framework\v4.0. Для 64-разрядных версий систем она находится в папке C:\windows\Microsoft.NET\Framework64\v4.0. Кроме того, доступны средства EdmGen.exe из командной строки Visual Studio (щелкните **запустить**, пункты **все программы**, пункты **Microsoft Visual Studio 2010**, пункты **Набора средств visual Studio**, а затем нажмите кнопку **Командная строка Visual Studio 2010**).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
EdmGen /mode:choice [options]  
```  
  
## <a name="mode"></a>Режим  
 При использовании средства EdmGen.exe необходимо указать один из следующих режимов.  
  
|Mode|Описание|  
|----------|-----------------|  
|`/mode:ValidateArtifacts`|Проверяет файлы CSDL, SSDL и MSL и отображает любые ошибки и предупреждения.<br /><br /> Для этого параметра необходим хотя бы один из аргументов `/inssdl` и `/incsdl`. Если указан аргумент `/inmsl`, также необходимо указать аргументы `/inssdl` и `/incsdl`.|  
|`/mode:FullGeneration`|Использует сведения о соединении с базой данных, указанные в параметре `/connectionstring`, и формирует файлы CSDL, SSDL, MSL, файлы уровня объектов и файлы представлений.<br /><br /> Для этого параметра необходим аргумент `/connectionstring`, а также аргумент `/project` или аргументы `/outssdl`, `/outcsdl`, `/outmsdl`, `/outobjectlayer`, `/outviews`, `/namespace` и `/entitycontainer`.|  
|`/mode:FromSSDLGeneration`|Создает файлы CSDL и MSL, исходный код и представления из указанного файла SSDL.<br /><br /> Для этого параметра необходим аргумент `/inssdl`, а также аргумент `/project` или аргументы `/outcsdl`, `/outmsl`, `/outobjectlayer`, `/outviews`, `/namespace,` и `/entitycontainer`.|  
|`/mode:EntityClassGeneration`|Создает файл с исходным кодом, в котором содержатся классы, сформированные на базе файла CSDL.<br /><br /> Для этого параметра необходим аргумент `/incsdl`, а также аргумент `/project` или аргумент `/outobjectlayer`. Аргумент `/language` не обязателен.|  
|`/mode:ViewGeneration`|Создает файл с исходным кодом, в котором содержатся представления, сформированные на базе файлов CSDL, SSDL и MSL.<br /><br /> Для этого параметра необходим аргументы `/inssdl`, `/incsdl`, `/inmsl,` а также аргумент `/project` или `/outviews`. Аргумент `/language` не обязателен.|  
  
## <a name="options"></a>Параметры  
  
|Параметр|Описание:|  
|------------|-----------------|  
|`/p[roject]:`\<string>|Задает используемое имя проекта. Имя проекта используется в качестве значения по умолчанию для параметра пространства имен, имен файлов модели и сопоставления, имени файла источника объекта и имени исходного файла создания представления. Имя контейнера сущностей равно \<проекта > контекста.|  
|`/prov[ider]:`\<string>|Имя поставщика данных [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] для создания файла модели хранения (SSDL). Поставщик по умолчанию [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] поставщик данных для SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>).|  
|`/c[onnectionstring]:`\<Строка подключения >|Задает строку, используемую для подключения к источнику данных.|  
|`/incsdl:`\<file>|Указывает CSDL-файл или каталог, в котором находятся CSDL-файлы. Этот аргумент может быть задан несколько раз, поэтому можно назначить несколько каталогов или CSDL-файлов. Назначение нескольких каталогов может быть полезным для формирования классов (`/mode:EntityClassGeneration`) или представлений (`/mode:ViewGeneration`), когда концептуальная модель разбита между несколькими файлами. Эта возможность также полезна, когда требуется оценить несколько моделей (`/mode:ValidateArtifacts`).|  
|`/refcsdl:`\<file>|Задает дополнительный CSDL-файл или файлы, используемые для разрешения любых ссылок на исходный CSDL-файл. (Исходный CSDL-файл это тот файл, который задан параметром `/incsdl`.) Файл `/refcsdl` содержит типы, от которых зависит исходный CSDL-файл. Этот аргумент может быть задан несколько раз.|  
|`/inmsl:`\<file>|Указывает MSL-файл или каталог, в котором находятся MSL-файлы. Этот аргумент может быть задан несколько раз, поэтому можно назначить несколько каталогов или MSL-файлов. Назначение нескольких каталогов может быть полезным для формирования представлений (`/mode:ViewGeneration`), когда концептуальная модель разбита между несколькими файлами. Эта возможность также полезна, когда требуется оценить несколько моделей (`/mode:ValidateArtifacts`).|  
|`/inssdl:`\<file>|Указывает SSDL-файл или каталог, в котором находятся SSDL-файлы. Этот аргумент может быть задан несколько раз, поэтому можно назначить несколько каталогов или SSDL-файлов. Эта возможность полезна, когда требуется оценить несколько моделей `(/mode:ValidateArtifacts)`.|  
|`/outcsdl:`\<file>|Задает имя создаваемого CSDL-файла.|  
|`/outmsl:`\<file>|Задает имя создаваемого MSL-файла.|  
|`/outssdl:`\<file>|Задает имя создаваемого SSDL-файла.|  
|`/outobjectlayer:`\<file>|Задает имя файла с исходным кодом, в котором содержатся объекты, сформированные из CSDL-файла.|  
|`/outviews:`\<file>|Задает имя файла с исходным кодом, в котором содержатся сформированные представления.|  
|`/language:`[VB&#124;CSharp]|Задает язык для сформированных файлов с исходным кодом. Язык по умолчанию — C#.|  
|`/namespace:`\<string>|Задает используемое пространство имен модели. Пространство имен задается в CSDL-файле при выполнении `/mode:FullGeneration` или `/mode:FromSSDLGeneration`. Пространство имен не используется при выполнении `/mode:EntityClassGeneration`.|  
|`/entitycontainer:`\<string>|Задает имя, применяемое к элементу `<EntityContainer>` в созданных файлах модели и сопоставлениях.|  
|`/pl[uralize]`|Применяет к концептуальной модели правила английского языка для форм единственного и множественного числа в именах `Entity`, `EntitySet` и `NavigationProperty`. Этот параметр выполняет следующие действия:<br /><br /> -Убедитесь, все `EntityType` имена в единственном числе.<br />-Убедитесь, все `EntitySet` имена во множественном числе.<br />-Для каждого `NavigationProperty` , возвращающего не более одной сущности, сделайте имя в единственном числе.<br />-Для каждого `NavigationProperty` , возвращающий несколько сущностей, используйте имена во множественном числе.|  
|`/SupressForeignKeyProperties or /nofk`|Предотвращает раскрытие столбцов внешних ключей в виде скалярных свойств в типах сущностей концептуальной модели.|  
|`/help` или `?`|Отображает синтаксис команд и параметров программы.|  
|`/nologo`|Отключает вывод сообщения об авторских правах.|  
|`/targetversion:` \<string>|Версия платформы .NET Framework, которая будет использоваться для компиляции сформированного кода. Поддерживаемыми версиями являются 4 и 4.5. Значение по умолчанию — 4.|  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Использование EdmGen.exe для создания файлов модели и сопоставления](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)  
  
 [Практическое руководство. Использование EdmGen.exe для создания кода объектного уровня](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)  
  
 [Практическое руководство. Использование EdmGen.exe для проверки файлов модели и сопоставления](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)  
  
## <a name="see-also"></a>См. также  
 [Средства работы с моделью EDM ADO.NET](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [Сущностная модель данных](../../../../../docs/framework/data/adonet/entity-data-model.md)  
 [Спецификации CSDL, SSDL и MSL](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
