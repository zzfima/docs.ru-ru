---
title: "Строки соединения и файлы конфигурации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 37df2641-661e-407a-a3fb-7bf9540f01e8
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Строки соединения и файлы конфигурации
Внедрение строк соединения в код приложения может привести к появлению уязвимых мест в системе безопасности и проблем с обслуживанием.  Незашифрованные строки соединения, скомпилированные в исходный код приложения, можно просматривать с помощью средства [Ildasm.exe \(IL Disassembler\)](../../../../docs/framework/tools/ildasm-exe-il-disassembler.md).  Кроме того, после изменения строки соединения необходимо перекомпилировать приложение.  По этим причинам рекомендуется хранить строки соединения в файле конфигурации приложения.  
  
## Работа с файлами конфигурации приложения  
 Файлы конфигурации приложения содержат настройки, относящиеся к отдельному приложению.  Например, приложение ASP.NET может иметь один или несколько файлов **web.config**, а приложение Windows может иметь дополнительный файл **app.config**.  В файлах конфигурации присутствуют общие элементы, хотя имя и расположение любого файла конфигурации в значительной степени зависят от того, где размещается приложение.  
  
### Раздел connectionStrings  
 Строки соединения могут храниться в виде пар «ключ\/значение» в разделе **connectionStrings** элемента **configuration** файла конфигурации приложения.  Дочерние элементы включают **add**, **clear** и **remove**.  
  
 Следующий фрагмент файла конфигурации демонстрирует схему и синтаксис хранения строки соединения.  Атрибут **name** является именем, которое задано для уникальной идентификации строки соединения, чтобы ее можно было получить во время выполнения.  Атрибут **providerName** является неизменяемым именем поставщика данных .NET Framework, которое регистрируется в файле machine.config.  
  
```  
<?xml version='1.0' encoding='utf-8'?>  
  <configuration>  
    <connectionStrings>  
      <clear />  
      <add name="Name"   
       providerName="System.Data.ProviderName"   
       connectionString="Valid Connection String;" />  
    </connectionStrings>  
  </configuration>  
```  
  
> [!NOTE]
>  Можно сохранить часть строки соединения в файле конфигурации и для ее дополнения во время выполнения использовать класс <xref:System.Data.Common.DbConnectionStringBuilder>.  Это удобно в сценариях, в которых заранее неизвестны элементы строки соединения или желательно не сохранять конфиденциальные данные в файле конфигурации.  Для получения дополнительной информации см. [Построители строк подключения](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
### Использование внешних файлов конфигурации  
 Внешние файлы конфигурации представляют собой отдельные файлы, каждый из которых содержит фрагмент файла конфигурации, состоящий из одного раздела.  В таком случае основной файл конфигурации ссылается на внешний файл конфигурации.  Хранение раздела **connectionStrings** в физически отдельном файле становится удобным в ситуациях, когда может потребоваться внесение изменений в строки соединения после развертывания приложения.  Например, в ASP.NET по умолчанию после изменения файлов конфигурации осуществляется перезапуск домена приложения, что приводит к потере сведений о состоянии.  Но изменение внешнего файла конфигурации не вызывает перезапуск приложения.  Возможность применения внешних файлов конфигурации не ограничивается ASP.NET; их можно также использовать в приложениях Windows.  Кроме того, для ограничения доступа к внешним файлам конфигурации могут использоваться средства обеспечения безопасности доступа к файлам и разрешения.  Работа с внешними файлами конфигурации во время выполнения осуществляется в прозрачном режиме и не требует разработки специального кода.  
  
 Для хранения строк соединения во внешнем файле конфигурации создайте отдельный файл, содержащий единственный раздел **connectionStrings**.  Не следует включать какие\-либо дополнительные элементы, разделы или атрибуты.  В данном примере показан синтаксис внешнего файла конфигурации.  
  
```  
<connectionStrings>  
  <add name="Name"   
   providerName="System.Data.ProviderName"   
   connectionString="Valid Connection String;" />  
</connectionStrings>  
```  
  
 В основном файле конфигурации приложения для указания полного имени и расположения внешнего файла используется атрибут **configSource**.  В следующем примере применяется ссылка на внешний файл конфигурации с именем `connections.config`.  
  
```  
<?xml version='1.0' encoding='utf-8'?>  
<configuration>  
    <connectionStrings configSource="connections.config"/>  
</configuration>  
```  
  
## Получение строк соединения во время выполнения  
 В .NET Framework 2.0 в пространстве имен <xref:System.Configuration> появились новые классы, упрощающие извлечение строк подключения из файлов конфигурации во время выполнения.  Предусмотрена возможность получить строку соединения программным путем по ее имени или по имени поставщика.  
  
> [!NOTE]
>  Файл **machine.config** также содержит раздел **connectionStrings**, включающий в себя строку соединения, используемую Visual Studio.  При получении строк соединения из файла **app.config** приложения Windows с помощью имени поставщика в первую очередь загружаются строки соединения из файла **machine.config**, затем записи из файла **app.config**.  Добавление ключевого слова **clear** сразу после элемента **connectionStrings** приводит к удалению из памяти всех ссылок, унаследованных от структуры данных, поэтому учитываются только строки соединения, определенные в локальном файле **app.config**.  
  
### Работа с классами конфигурации  
 Начиная с версии .NET Framework 2.0, для работы с файлами конфигурации на локальном компьютере используется класс <xref:System.Configuration.ConfigurationManager>, который заменил устаревший класс <xref:System.Configuration.ConfigurationSettings>.  <xref:System.Web.Configuration.WebConfigurationManager> служит для работы с файлами конфигурации ASP.NET.  Он создан для работы с файлами конфигурации веб\-сервера и предоставляет программный доступ к разделам файла конфигураций, например **system.web**.  
  
> [!NOTE]
>  Вызывающему объекту для доступа к файлам конфигурации во время выполнения должны быть предоставлены разрешения. Требуемые разрешения зависят от типа приложения, файла конфигурации и расположения.  Дополнительные сведения см. в разделах [Using the Configuration Classes](../Topic/Using%20the%20Configuration%20Classes.md) и <xref:System.Web.Configuration.WebConfigurationManager> для приложений ASP.NET и <xref:System.Configuration.ConfigurationManager> для приложений Windows.  
  
 Для получения строк соединения из файлов конфигурации приложения используется <xref:System.Configuration.ConnectionStringSettingsCollection>.  Этот объект содержит коллекцию объектов <xref:System.Configuration.ConnectionStringSettings>, каждый из которых представляет одну запись в разделе **connectionStrings**.  Его свойства сопоставляются с атрибутами строк соединения, что позволяет получить строку соединения, указав имя строки или имя поставщика.  
  
|Свойство|Описание|  
|--------------|--------------|  
|<xref:System.Configuration.ConnectionStringSettings.Name%2A>|Имя строки соединения.  Сопоставляется с атрибутом **name**.|  
|<xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>|Полное имя поставщика.  Сопоставляется с атрибутом **providerName**.|  
|<xref:System.Configuration.ConnectionStringSettings.ConnectionString%2A>|Строка подключения.  Сопоставляется с атрибутом **connectionString**.|  
  
### Пример. Список всех строк соединения  
 В данном примере выполняется итерация в коллекции `ConnectionStringSettings` и отображение свойств <xref:System.Configuration.ConnectionStringSettings.Name%2A>, <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> и <xref:System.Configuration.ConnectionStringSettings.ConnectionString%2A> в окне консоли.  
  
> [!NOTE]
>  Файл System.Configuration.dll не включается в проекты всех типов, поэтому для использования классов конфигурации может потребоваться сформировать на него ссылку.  Имя и расположение файла конфигурации определенного приложения зависит от типа приложения и процесса размещения.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfig#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfig/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfig#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfig/VB/source.vb#1)]  
  
### Пример. Извлечение строки соединения по имени  
 Данный пример демонстрирует способ получения строки соединения из файла конфигурации путем указания ее имени.  Код создает объект <xref:System.Configuration.ConnectionStringSettings>, сопоставляя указанный входной параметр с именем <xref:System.Configuration.ConfigurationManager.ConnectionStrings%2A>.  Если совпадающее имя не найдено, функция возвращает значение `null` \(`Nothing` в Visual Basic\).  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByName#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByName/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByName#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByName/VB/source.vb#1)]  
  
### Пример. Извлечение строки соединения по имени поставщика  
 В данном примере демонстрируется способ получения строки соединения путем указания неизменяемого имени поставщика в формате *System.Data.ProviderName*.  В коде выполняется итерация по <xref:System.Configuration.ConnectionStringSettingsCollection> и происходит возврат строки соединения для первого найденного <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>.  Если имя поставщика не найдено, функция возвращает значение `null` \(`Nothing` в Visual Basic\).  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## Шифрование разделов файлов конфигурации с использованием защищенной конфигурации  
 В ASP.NET 2.0 появилась новая возможность, *защищенная конфигурация*, с помощью которой можно шифровать в файле конфигурации конфиденциальную информацию.  Защищенная конфигурация разрабатывалась в первую очередь для ASP.NET, но ее можно также использовать для шифрования разделов файлов конфигурации в приложениях Windows.  Подробное описание новых возможностей защищенной конфигурации см. в разделе [Encrypting Configuration Information Using Protected Configuration](../Topic/Encrypting%20Configuration%20Information%20Using%20Protected%20Configuration.md).  
  
 В приведенном ниже фрагменте файла конфигурации показан раздел **connectionStrings** после шифрования.  В разделе **configProtectionProvider** задается поставщик защищенной конфигурации, который используется для шифрования и дешифрования строк соединения.  Раздел **EncryptedData** содержит зашифрованный текст.  
  
```  
<connectionStrings configProtectionProvider="DataProtectionConfigurationProvider">  
  <EncryptedData>  
    <CipherData>  
      <CipherValue>AQAAANCMnd8BFdERjHoAwE/Cl+sBAAAAH2... </CipherValue>  
    </CipherData>  
  </EncryptedData>  
</connectionStrings>  
```  
  
 Когда зашифрованная строка подключения извлекается во время выполнения, платформа .NET Framework с помощью указанного поставщика дешифрует значение **CipherValue** и передает его приложению.  Нет необходимости создавать дополнительный код для управления процессом дешифрования.  
  
### Поставщики защищенной конфигурации  
 Поставщики защищенной конфигурации регистрируются в разделе **configProtectedData** файла **machine.config** на локальном компьютере, как показано в приведенном ниже фрагменте, в котором демонстрируется два поставщика защищенной конфигурации, поставляемые с платформой .NET Framework.  Показанные значения были усечены для удобства чтения.  
  
```  
<configProtectedData defaultProvider="RsaProtectedConfigurationProvider">  
  <providers>  
    <add name="RsaProtectedConfigurationProvider"   
      type="System.Configuration.RsaProtectedConfigurationProvider, ... />  
    <add name="DataProtectionConfigurationProvider"   
      type="System.Configuration.DpapiProtectedConfigurationProvider, ... />  
  </providers>  
</configProtectedData>  
```  
  
 Можно назначить дополнительные поставщики защищенной конфигурации, добавляя их в файл **machine.config**.  Кроме того, можно создать собственный поставщик защищенной конфигурации путем наследования от абстрактного базового класса <xref:System.Configuration.ProtectedConfigurationProvider>.  В приведенной ниже таблице дано описание двух файлов конфигурации, входящих в платформу .NET Framework.  
  
|Поставщик|Описание|  
|---------------|--------------|  
|<xref:System.Configuration.RSAProtectedConfigurationProvider>|Использует алгоритм RSA для шифрования и расшифровки данных.  Алгоритм RSA можно использовать для шифрования с открытым ключом и цифровых сигнатур.  Он также известен как алгоритм с «открытым ключом» или алгоритм асимметричного шифрования, поскольку в нем используется два разных ключа.  Для шифрования разделов в файле Web.config и управления ключами шифрования можно использовать средство [ASP.NET IIS Registration Tool \(Aspnet\_regiis.exe\)](../Topic/ASP.NET%20IIS%20Registration%20Tool%20\(Aspnet_regiis.exe\).md).  ASP.NET расшифровывает файл конфигурации при обработке файла.  Удостоверение приложения ASP.NET должно иметь права на чтение ключа шифрования, который используется для шифрования и расшифровки зашифрованных разделов.|  
|<xref:System.Configuration.DPAPIProtectedConfigurationProvider>|Использует API\-интерфейс защиты данных \(DPAPI\) для шифрования разделов конфигурации.  Он использует встроенные службы шифрования Windows и может быть настроен для защиты отдельных компьютеров или отдельных учетных записей пользователей.  Защиту отдельных компьютеров удобно использовать для нескольких приложений на одном сервере, которым требуется совместное использование данных.  Защиту учетных записей можно использовать со службами, выполняемыми с определенным удостоверением пользователя, например с общей средой размещения.  Каждое приложение выполняется с отдельным удостоверением, которое ограничивает доступ к ресурсам, например к файлам и базам данных.|  
  
 Оба поставщика обеспечивают надежное шифрование данных.  Однако, если планируется использовать один файл конфигурации на нескольких серверах, как в веб\-ферме, то только `RsaProtectedConfigurationProvider` позволяет экспортировать ключи шифрования, применяемые для шифрования данных, и импортировать их в другой сервер.  Для получения дополнительной информации см. [Importing and Exporting Protected Configuration RSA Key Containers](../Topic/Importing%20and%20Exporting%20Protected%20Configuration%20RSA%20Key%20Containers.md).  
  
### Использование классов конфигурации  
 Пространство имен <xref:System.Configuration> предоставляет классы для программной обработки параметров конфигурации.  Класс <xref:System.Configuration.ConfigurationManager> обеспечивает доступ к компьютеру, приложению и пользовательским файлам конфигурации.  При создании приложения ASP.NET можно использовать класс <xref:System.Web.Configuration.WebConfigurationManager>, который предоставляет те же функциональные возможности и одновременно позволяет обращаться к уникальным настройкам приложений ASP.NET, в частности, в файле **\<system.web\>**.  
  
> [!NOTE]
>  Пространство имен <xref:System.Security.Cryptography> содержит классы, которые предоставляют дополнительные возможности шифрования и расшифровки данных.  Эти классы можно использовать в том случае, если требуются криптографические службы, недоступные с использованием защищенной конфигурации.  Некоторые из этих классов являются оболочками для Microsoft CryptoAPI, а другие представляют собой реализации полностью на управляемом коде.  Для получения дополнительной информации см. [Cryptographic Services](http://msdn.microsoft.com/ru-ru/68a1e844-c63c-44af-9247-f6716eb23781).  
  
### Пример App.config  
 Этот пример демонстрирует переключение шифрования раздела **connectionStrings** в файле **app.config** для приложения Windows.  В этом примере процедура принимает имя приложения в качестве аргумента, например, «MyApplication.exe».  Затем файл **app.config** зашифровывается и копируется в папку, которая содержит исполняемый файл с именем «MyApplication.exe.config».  
  
> [!NOTE]
>  Строку соединения можно расшифровать только на компьютере, где она была зашифрована.  
  
 В коде используется метод <xref:System.Configuration.ConfigurationManager.OpenExeConfiguration%2A>, чтобы открыть файл **app.config** для изменения, а метод <xref:System.Configuration.ConfigurationManager.GetSection%2A> возвращает раздел **connectionStrings**.  Затем код проверяет свойство <xref:System.Configuration.SectionInformation.IsProtected%2A>, вызывая метод <xref:System.Configuration.SectionInformation.ProtectSection%2A> для шифрования раздела, если он не зашифрован.  Метод <xref:System.Configuration.SectionInformation.UnProtectSection%2A> вызывается для расшифровки раздела.  Метод <xref:System.Configuration.Configuration.Save%2A> завершает операцию и сохраняет изменения.  
  
> [!NOTE]
>  Для запуска кода необходимо задать ссылку на `System.Configuration.dll` в проекте.  
  
 [!code-csharp[DataWorks ConnectionStrings.Encrypt#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStrings.Encrypt/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStrings.Encrypt#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStrings.Encrypt/VB/source.vb#1)]  
  
### Пример Web.config  
 В этом примере используется метод <xref:System.Web.Configuration.WebConfigurationManager.OpenWebConfiguration%2A> класса `WebConfigurationManager`.  Обратите внимание, что в этом случае можно задать относительный путь к файлу **Web.config** с использованием символа «тильда».  В коде должна быть ссылка на класс `System.Web.Configuration`.  
  
 [!code-csharp[DataWorks ConnectionStringsWeb.Encrypt#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringsWeb.Encrypt/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringsWeb.Encrypt#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringsWeb.Encrypt/VB/source.vb#1)]  
  
 Дополнительные сведения о защите приложений ASP.NET см. в разделе [NIB: ASP.NET Security](http://msdn.microsoft.com/ru-ru/04b37532-18d9-40b4-8e5f-ee09a70b311d) и [ASP.NET 2.0 Security Practices at a Glance](http://go.microsoft.com/fwlink/?LinkId=59997) в центре разработчиков ASP.NET.  
  
## См. также  
 [Построители строк подключения](../../../../docs/framework/data/adonet/connection-string-builders.md)   
 [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md)   
 [Using the Configuration Classes](../Topic/Using%20the%20Configuration%20Classes.md)   
 [Настройка приложений](../../../../docs/framework/configure-apps/index.md)   
 [ASP.NET Web Site Administration](../Topic/ASP.NET%20Web%20Site%20Administration.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)