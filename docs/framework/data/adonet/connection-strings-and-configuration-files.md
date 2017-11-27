---
title: "Строки подключения и файлы конфигурации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 37df2641-661e-407a-a3fb-7bf9540f01e8
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fe56dc279471f77a3f9ae014f65faaa99a113624
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="connection-strings-and-configuration-files"></a>Строки подключения и файлы конфигурации
Внедрение строк соединения в код приложения может привести к появлению уязвимых мест в системе безопасности и проблем с обслуживанием. Незашифрованные строки соединения компилируются в исходном коде приложения можно просмотреть при помощи [Ildasm.exe (дизассемблер IL)](../../../../docs/framework/tools/ildasm-exe-il-disassembler.md) средства. Кроме того, после изменения строки соединения необходимо перекомпилировать приложение. По этим причинам рекомендуется хранить строки соединения в файле конфигурации приложения.  
  
## <a name="working-with-application-configuration-files"></a>Работа с файлами конфигурации приложения  
 Файлы конфигурации приложения содержат настройки, относящиеся к отдельному приложению. Например, приложение ASP.NET может иметь один или несколько **web.config** файлов и приложений Windows может иметь дополнительный **app.config** файла. В файлах конфигурации присутствуют общие элементы, хотя имя и расположение любого файла конфигурации в значительной степени зависят от того, где размещается приложение.  
  
### <a name="the-connectionstrings-section"></a>Раздел connectionStrings  
 Строки соединения можно сохранить в качестве пар ключ/значение в **connectionStrings** раздел **конфигурации** элемент файла конфигурации приложения. Дочерние элементы включают **добавить**, **снимите**, и **удалить**.  
  
 Следующий фрагмент файла конфигурации демонстрирует схему и синтаксис хранения строки соединения. **Имя** атрибута — это имя, укажите для уникальной идентификации строки подключения, чтобы можно было получить во время выполнения. **ProviderName** неизменяемое имя поставщика данных .NET Framework, которая зарегистрирована в файле machine.config.  
  
```xml  
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
>  Можно сохранить часть строки соединения в файле конфигурации и для ее дополнения во время выполнения использовать класс <xref:System.Data.Common.DbConnectionStringBuilder>. Это удобно в сценариях, в которых заранее неизвестны элементы строки соединения или желательно не сохранять конфиденциальные данные в файле конфигурации. Дополнительные сведения см. в разделе [построители строк соединения](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
### <a name="using-external-configuration-files"></a>Использование внешних файлов конфигурации  
 Внешние файлы конфигурации представляют собой отдельные файлы, каждый из которых содержит фрагмент файла конфигурации, состоящий из одного раздела. В таком случае основной файл конфигурации ссылается на внешний файл конфигурации. Хранение **connectionStrings** раздел в физически отдельном файле полезен в ситуациях, где строки подключения могут быть изменены после развертывания приложения. Например, в ASP.NET по умолчанию после изменения файлов конфигурации осуществляется перезапуск домена приложения, что приводит к потере сведений о состоянии. Но изменение внешнего файла конфигурации не вызывает перезапуск приложения. Возможность применения внешних файлов конфигурации не ограничивается ASP.NET; их можно также использовать в приложениях Windows. Кроме того, для ограничения доступа к внешним файлам конфигурации могут использоваться средства обеспечения безопасности доступа к файлам и разрешения. Работа с внешними файлами конфигурации во время выполнения осуществляется в прозрачном режиме и не требует разработки специального кода.  
  
 Для хранения строки подключения в внешнего файла конфигурации создайте отдельный файл, содержащий только **connectionStrings** раздела. Не следует включать какие-либо дополнительные элементы, разделы или атрибуты. В данном примере показан синтаксис внешнего файла конфигурации.  
  
```xml  
<connectionStrings>  
  <add name="Name"   
   providerName="System.Data.ProviderName"   
   connectionString="Valid Connection String;" />  
</connectionStrings>  
```  
  
 В файле конфигурации основного приложения используется **configSource** атрибут для указания полного имени и расположения внешнего файла. В следующем примере применяется ссылка на внешний файл конфигурации с именем `connections.config`.  
  
```xml  
<?xml version='1.0' encoding='utf-8'?>  
<configuration>  
    <connectionStrings configSource="connections.config"/>  
</configuration>  
```  
  
## <a name="retrieving-connection-strings-at-run-time"></a>Получение строк соединения во время выполнения  
 В .NET Framework 2.0 в пространстве имен <xref:System.Configuration> появились новые классы, упрощающие извлечение строк подключения из файлов конфигурации во время выполнения. Предусмотрена возможность получить строку соединения программным путем по ее имени или по имени поставщика.  
  
> [!NOTE]
>  **Machine.config** файл также содержит **connectionStrings** раздел, который содержит строки подключения, используемый в Visual Studio. При получении строк соединения по имени поставщика из **app.config** файл в приложении Windows, строки подключения в **machine.config** получить первую очередь загружаются, а затем записи из **app.config**. Добавление **снимите** сразу же после **connectionStrings** приводит к удалению всех ссылок, унаследованных из структуры данных в памяти, так что только строки соединения, определенные в локальном **app.config** считаются файла.  
  
### <a name="working-with-the-configuration-classes"></a>Работа с классами конфигурации  
 Начиная с версии .NET Framework 2.0, для работы с файлами конфигурации на локальном компьютере используется класс <xref:System.Configuration.ConfigurationManager>, который заменил устаревший класс <xref:System.Configuration.ConfigurationSettings>. <xref:System.Web.Configuration.WebConfigurationManager> служит для работы с файлами конфигурации ASP.NET. Он предназначен для работы с файлами конфигурации на веб-сервере и обеспечивает программный доступ к разделам файла конфигураций, такие как **system.web**.  
  
> [!NOTE]
>  Вызывающему объекту для доступа к файлам конфигурации во время выполнения должны быть предоставлены разрешения. Требуемые разрешения зависят от типа приложения, файла конфигурации и расположения. Дополнительные сведения см. в разделе [использование классов конфигурации](http://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc) и <xref:System.Web.Configuration.WebConfigurationManager> для приложений ASP.NET и <xref:System.Configuration.ConfigurationManager> для приложений Windows.  
  
 Для получения строк соединения из файлов конфигурации приложения используется <xref:System.Configuration.ConnectionStringSettingsCollection>. Он содержит коллекцию <xref:System.Configuration.ConnectionStringSettings> объектов, каждый из которых представляет одну запись в **connectionStrings** раздела. Его свойства сопоставляются с атрибутами строк соединения, что позволяет получить строку соединения, указав имя строки или имя поставщика.  
  
|Свойство|Описание|  
|--------------|-----------------|  
|<xref:System.Configuration.ConnectionStringSettings.Name%2A>|Имя строки соединения. Сопоставляет **имя** атрибута.|  
|<xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>|Полное имя поставщика. Сопоставляет **providerName** атрибута.|  
|<xref:System.Configuration.ConnectionStringSettings.ConnectionString%2A>|Строка подключения. Сопоставляет **connectionString** атрибута.|  
  
### <a name="example-listing-all-connection-strings"></a>Пример. Список всех строк соединения  
 В данном примере выполняется итерация в коллекции `ConnectionStringSettings` и отображение свойств <xref:System.Configuration.ConnectionStringSettings.Name%2A>, <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> и <xref:System.Configuration.ConnectionStringSettings.ConnectionString%2A> в окне консоли.  
  
> [!NOTE]
>  Файл System.Configuration.dll не включается в проекты всех типов, поэтому для использования классов конфигурации может потребоваться сформировать на него ссылку. Имя и расположение файла конфигурации определенного приложения зависит от типа приложения и процесса размещения.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfig#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfig/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfig#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfig/VB/source.vb#1)]  
  
### <a name="example-retrieving-a-connection-string-by-name"></a>Пример. Извлечение строки соединения по имени  
 Данный пример демонстрирует способ получения строки соединения из файла конфигурации путем указания ее имени. Код создает объект <xref:System.Configuration.ConnectionStringSettings>, сопоставляя указанный входной параметр с именем <xref:System.Configuration.ConfigurationManager.ConnectionStrings%2A>. Если совпадающее имя не найдено, функция возвращает значение `null` (`Nothing` в Visual Basic).  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByName#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByName/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByName#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByName/VB/source.vb#1)]  
  
### <a name="example-retrieving-a-connection-string-by-provider-name"></a>Пример. Извлечение строки соединения по имени поставщика  
 В этом примере показано, как получить строку соединения путем указания неизменяемого имени поставщика в формате *System.Data.ProviderName*. В коде выполняется итерация по <xref:System.Configuration.ConnectionStringSettingsCollection> и происходит возврат строки соединения для первого найденного <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>. Если имя поставщика не найдено, функция возвращает значение `null` (`Nothing` в Visual Basic).  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## <a name="encrypting-configuration-file-sections-using-protected-configuration"></a>Шифрование разделов файлов конфигурации с использованием защищенной конфигурации  
 ASP.NET 2.0 появилась новая возможность, *защищенной конфигурации*, который позволяет шифровать конфиденциальные данные в файле конфигурации. Защищенная конфигурация разрабатывалась в первую очередь для ASP.NET, но ее можно также использовать для шифрования разделов файлов конфигурации в приложениях Windows. Подробное описание возможностей защищенной конфигурации см. в разделе [шифрование конфигурации сведения с помощью защищенной конфигурации](http://msdn.microsoft.com/library/51cdfe5b-9d82-458c-94ff-c551c4f38ed1).  
  
 В следующем файле конфигурации фрагмент показывает **connectionStrings** статьи после он зашифрован. **ConfigProtectionProvider** задается поставщик защищенной конфигурации, используется для шифрования и дешифрования строк соединения. **EncryptedData** раздел содержит зашифрованный текст.  
  
```xml  
<connectionStrings configProtectionProvider="DataProtectionConfigurationProvider">  
  <EncryptedData>  
    <CipherData>  
      <CipherValue>AQAAANCMnd8BFdERjHoAwE/Cl+sBAAAAH2... </CipherValue>  
    </CipherData>  
  </EncryptedData>  
</connectionStrings>  
```  
  
 Когда зашифрованная строка подключения извлекается во время выполнения, платформа .NET Framework с помощью указанного поставщика для расшифровки **CipherValue** и сделать его доступным для приложения. Нет необходимости создавать дополнительный код для управления процессом дешифрования.  
  
### <a name="protected-configuration-providers"></a>Поставщики защищенной конфигурации  
 Поставщики защищенной конфигурации регистрируются в **configProtectedData** раздел **machine.config** файлов на локальном компьютере, как показано в следующем фрагменте показано два поставщики защищенной конфигурации, поставляемых вместе с .NET Framework. Показанные значения были усечены для удобства чтения.  
  
```xml  
<configProtectedData defaultProvider="RsaProtectedConfigurationProvider">  
  <providers>  
    <add name="RsaProtectedConfigurationProvider"   
      type="System.Configuration.RsaProtectedConfigurationProvider, ... />  
    <add name="DataProtectionConfigurationProvider"   
      type="System.Configuration.DpapiProtectedConfigurationProvider, ... />  
  </providers>  
</configProtectedData>  
```  
  
 Можно настроить дополнительные поставщики защищенной конфигурации, добавив их в **machine.config** файла. Кроме того, можно создать собственный поставщик защищенной конфигурации путем наследования от абстрактного базового класса <xref:System.Configuration.ProtectedConfigurationProvider>. В приведенной ниже таблице дано описание двух файлов конфигурации, входящих в платформу .NET Framework.  
  
|Поставщик|Описание|  
|--------------|-----------------|  
|<!--zz<xref:System.Configuration.RSAProtectedConfigurationProvider>-->`System.Configuration.RSAProtectedConfigurationProvider`|Использует алгоритм RSA для шифрования и расшифровки данных. Алгоритм RSA можно использовать для шифрования с открытым ключом и цифровых сигнатур. Он также известен как алгоритм с «открытым ключом» или алгоритм асимметричного шифрования, поскольку в нем используется два разных ключа. Можно использовать [средство регистрации ASP.NET IIS (Aspnet_regiis.exe)](http://msdn.microsoft.com/library/6491c41e-e2b0-481f-9863-db3614d5f96b) для шифрования разделов в файле Web.config и управления ключами шифрования. ASP.NET расшифровывает файл конфигурации при обработке файла. Удостоверение приложения ASP.NET должно иметь права на чтение ключа шифрования, который используется для шифрования и расшифровки зашифрованных разделов.|  
|<!--zz<xref:System.Configuration.DPAPIProtectedConfigurationProvider>-->`System.Configuration.DPAPIProtectedConfigurationProvider`|Использует API-интерфейс защиты данных (DPAPI) для шифрования разделов конфигурации. Он использует встроенные службы шифрования Windows и может быть настроен для защиты отдельных компьютеров или отдельных учетных записей пользователей. Защиту отдельных компьютеров удобно использовать для нескольких приложений на одном сервере, которым требуется совместное использование данных. Защиту учетных записей можно использовать со службами, выполняемыми с определенным удостоверением пользователя, например с общей средой размещения. Каждое приложение выполняется с отдельным удостоверением, которое ограничивает доступ к ресурсам, например к файлам и базам данных.|  
  
 Оба поставщика обеспечивают надежное шифрование данных. Однако, если планируется использовать один файл конфигурации на нескольких серверах, как в веб-ферме, то только `RsaProtectedConfigurationProvider` позволяет экспортировать ключи шифрования, применяемые для шифрования данных, и импортировать их в другой сервер. Дополнительные сведения см. в разделе [Импорт и экспорт защищенных контейнеров ключей RSA](http://msdn.microsoft.com/library/f3022b39-f17f-48c1-b067-025eab0ce8bc).  
  
### <a name="using-the-configuration-classes"></a>Использование классов конфигурации  
 Пространство имен <xref:System.Configuration> предоставляет классы для программной обработки параметров конфигурации. Класс <xref:System.Configuration.ConfigurationManager> обеспечивает доступ к компьютеру, приложению и пользовательским файлам конфигурации. Если вы создаете приложения ASP.NET, можно использовать <xref:System.Web.Configuration.WebConfigurationManager> класса, который предоставляет те же функциональные возможности, а также позволяет получить доступ к параметрам, которые являются уникальными для приложений ASP.NET, например те, найденные в  **\< System.Web >**.  
  
> [!NOTE]
>  Пространство имен <xref:System.Security.Cryptography> содержит классы, которые предоставляют дополнительные возможности шифрования и расшифровки данных. Эти классы можно использовать в том случае, если требуются криптографические службы, недоступные с использованием защищенной конфигурации. Некоторые из этих классов являются оболочками для Microsoft CryptoAPI, а другие представляют собой реализации полностью на управляемом коде. Дополнительные сведения см. в разделе [службы криптографии](http://msdn.microsoft.com/en-us/68a1e844-c63c-44af-9247-f6716eb23781).  
  
### <a name="appconfig-example"></a>Пример App.config  
 Этот пример демонстрирует переключение шифрования **connectionStrings** статьи **app.config** файла для приложения Windows. В этом примере процедура принимает имя приложения в качестве аргумента, например, «MyApplication.exe». **App.config** файл будет зашифровывается и копируется в папку, которая содержит исполняемый файл с именем «MyApplication.exe.config»».  
  
> [!NOTE]
>  Строку соединения можно расшифровать только на компьютере, где она была зашифрована.  
  
 Код использует <xref:System.Configuration.ConfigurationManager.OpenExeConfiguration%2A> метод, чтобы открыть **app.config** файл для редактирования и <xref:System.Configuration.ConfigurationManager.GetSection%2A> возвращает **connectionStrings** раздела. Затем код проверяет свойство <xref:System.Configuration.SectionInformation.IsProtected%2A>, вызывая метод <xref:System.Configuration.SectionInformation.ProtectSection%2A> для шифрования раздела, если он не зашифрован. Метод <xref:System.Configuration.SectionInformation.UnprotectSection%2A> вызывается для расшифровки раздела. Метод <xref:System.Configuration.Configuration.Save%2A> завершает операцию и сохраняет изменения.  
  
> [!NOTE]
>  Для запуска кода необходимо задать ссылку на `System.Configuration.dll` в проекте.  
  
 [!code-csharp[DataWorks ConnectionStrings.Encrypt#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStrings.Encrypt/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStrings.Encrypt#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStrings.Encrypt/VB/source.vb#1)]  
  
### <a name="webconfig-example"></a>Пример Web.config  
 В этом примере используется метод <xref:System.Web.Configuration.WebConfigurationManager.OpenWebConfiguration%2A> класса `WebConfigurationManager`. Обратите внимание, что в этом случае можно задать относительный путь к **Web.config** файла с помощью тильды. В коде должна быть ссылка на класс `System.Web.Configuration`.  
  
 [!code-csharp[DataWorks ConnectionStringsWeb.Encrypt#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringsWeb.Encrypt/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringsWeb.Encrypt#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringsWeb.Encrypt/VB/source.vb#1)]  
  
 Дополнительные сведения, обеспечение безопасности приложений ASP.NET см. в разделе [NIB: безопасность ASP.NET](http://msdn.microsoft.com/en-us/04b37532-18d9-40b4-8e5f-ee09a70b311d) и [по обеспечению безопасности ASP.NET 2.0 с первого взгляда](http://go.microsoft.com/fwlink/?LinkId=59997) в центре разработчиков ASP.NET.  
  
## <a name="see-also"></a>См. также  
 [Построители строк подключения](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 [Защита сведений о подключении](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 [Использование классов конфигурации](http://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc)  
 [Настройка приложений](../../../../docs/framework/configure-apps/index.md)  
 [Администрирование веб-сайта ASP.NET](http://msdn.microsoft.com/library/1298034b-5f7d-464d-abd1-ad9e6b3eeb7e)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
