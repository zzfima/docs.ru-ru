---
title: "Практическое руководство.Определение установленных версий платформы .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "04/07/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "платформа .NET Framework, определение версии"
  - "версии, определение для .NET Framework"
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
caps.latest.revision: 62
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 53
---
# Практическое руководство.Определение установленных версий платформы .NET Framework
На компьютере можно установить и запустить несколько версий платформы .NET Framework. При разработке или развертывании приложения могут потребоваться сведения о том, какие версии .NET Framework установлены на компьютере пользователя. Учтите, что платформа .NET Framework состоит из основных компонентов, версии которым присваиваются отдельно:  
  
-   набор сборок, которые являются коллекциями типов и ресурсов, обеспечивающих функции приложений \(.NET Framework и сборкам назначается один номер версии\);  
  
-   среда CLR, которая выполняет код приложения и управляет им. Среде CLR присваивается собственный номер версии \(см. [Версии и зависимости](../../../docs/framework/migration-guide/versions-and-dependencies.md)\).  
  
 Чтобы получить точный список версий .NET Framework, установленных на компьютере, можно просмотреть реестр или отправить запрос в реестр с помощью кода:  
  
 [Просмотр реестра \(версии 1\-4\)](#net_a)  
[Просмотр реестра \(версии 4.5 и более поздние версии\)](#net_b)  
[Использование кода для отправки запроса в реестр \(версии 1–4\)](#net_c)  
[Использование кода для отправки запроса в реестр \(версия 4.5 и более поздние\)](#net_d)  
  
 Чтобы узнать версию среды CLR, можно использовать специальное средство или код:  
  
 [Использование средства Clrver](#clr_a)  
[Использование кода для отправки запроса в класс System.Environment](#clr_b)  
  
 Сведения об обнаружении установленных обновлений для каждой версии платформы .NET Framework см. в разделе [Практическое руководство.Определение установленных обновлений платформы .NET Framework](../../../docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md). Сведения об установке .NET Framework см. в [руководстве по установке](../../../docs/framework/install/guide-for-developers.md).  
  
<a name="net_a"></a>   
#### Поиск версий .NET Framework путем просмотра реестра \(.NET Framework 1–4\)  
  
1.  В меню **Пуск** выберите **Выполнить**.  
  
2.  В поле **Открыть** введите **regedit.exe**.  
  
     Для запуска regedit.exe необходимы учетные данные администратора.  
  
3.  В редакторе реестра откройте следующий подраздел:  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     Установленные версии перечислены в подразделе NDP. Номер версии хранится в записи **Version**. Для [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] запись **Version** находится в подразделе Client или Full \(внутри подраздела NDP\) либо в обоих подразделах.  
  
    > [!NOTE]
    >  Папка NET Framework Setup в реестре не начинается с точки.  
  
<a name="net_b"></a>   
#### Поиск версий .NET Framework путем просмотра реестра \(.NET Framework 4.5 и более поздних версий\)  
  
1.  В меню **Пуск** выберите **Выполнить**.  
  
2.  В поле **Открыть** введите **regedit.exe**.  
  
     Для запуска regedit.exe необходимы учетные данные администратора.  
  
3.  В редакторе реестра откройте следующий подраздел:  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`  
  
     Обратите внимание, что путь к подразделу `Full` включает подраздел `Net Framework` вместо `.NET Framework`.  
  
    > [!NOTE]
    >  Если подраздел `Full` отсутствует, платформа .NET Framework 4.5 или более поздней версии не установлена.  
  
     Проверьте значение DWORD с именем `Release`. Наличие DWORD `Release` указывает, что на компьютере установлена [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более новая версия.  
  
     ![Запись реестра для .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR\_InstallDir")  
  
     Значение DWORD `Release` показывает, какая версия .NET Framework установлена.  
  
    |Значение DWORD "Release"|Версия|  
    |------------------------------|------------|  
    |378389|.NET Framework 4,5|  
    |378675|Платформа .NET Framework 4.5.1, установленная с Windows 8.1 или Windows Server 2012 R2|  
    |378758|Платформа .NET Framework 4.5.1, установленная в Windows 8, Windows 7 с пакетом обновления 1 \(SP1\) или Windows Vista с пакетом обновления 2 \(SP2\)|  
    |379893|.NET Framework 4.5.2|  
    |В системах Windows 10: 393295<br /><br /> Во всех других версиях ОС: 393297|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|  
    |В системах Windows 10 с ноябрьским обновлением: 394254<br /><br /> Во всех других версиях ОС: 394271|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|  
  
<a name="net_c"></a>   
#### Поиск версий .NET Framework путем отправки запроса в реестр \(.NET Framework 1–4\)  
  
-   Используйте класс <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> для доступа к подразделу Software\\Microsoft\\NET Framework Setup\\NDP\\ в разделе HKEY\_LOCAL\_MACHINE в реестре Windows.  
  
     В следующем коде показан пример этого запроса.  
  
    > [!NOTE]
    >  В этом коде не показано, как обнаружить платформу [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более поздней версии. Для обнаружения этих версий проверьте DWORD `Release`, как описано в предыдущем разделе.  
  
     [!code-csharp[ListVersions#0](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#0)]
     [!code-vb[ListVersions#0](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#0)]  
    [!code-csharp[ListVersions#1](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#1)]
    [!code-vb[ListVersions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#1)]  
  
     Выходные данные этого примера выглядят примерно следующим образом:  
  
    ```  
  
    v2.0.50727  2.0.50727.4016  SP2 v3.0  3.0.30729.4037  SP2 v3.5  3.5.30729.01  SP1 v4 Client  4.0.30319 Full  4.0.30319  
    ```  
  
<a name="net_d"></a>   
#### Поиск версий .NET Framework путем отправки запроса в реестр \(.NET Framework 4.5 и более поздних версий\)  
  
1.  Наличие значения DWORD `Release` указывает, что на компьютере установлена платформа .NET Framework 4.5 или более поздней версии. Значение ключевого слова указывает на установленную версию. Чтобы проверить это ключевое слово, используйте методы <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> и <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> класса <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> для доступа к подразделу Software\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full в разделе HKEY\_LOCAL\_MACHINE реестра Windows.  
  
2.  Проверьте значение ключевого слова `Release`, чтобы определить установленную версию. Для обеспечения совместимости с последующими версиями значение должно быть больше или равно значениям, указанным в таблице. Ниже приведен список версий .NET Framework и соответствующих ключевых слов `Release`.  
  
    |Версия|Значение DWORD "Release"|  
    |------------|------------------------------|  
    |.NET Framework 4,5|378389|  
    |Платформа .NET Framework 4.5.1, установленная с Windows 8.1|378675|  
    |Платформа .NET Framework 4.5.1, установленная в Windows 8, Windows 7 с пакетом обновления 1 \(SP1\) или Windows Vista с пакетом обновления 2 \(SP2\)|378758|  
    |.NET Framework 4.5.2|379893|  
    |Платформа [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], установленная с Windows 10|393295|  
    |Платформа [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], установленная во всех остальных версиях ОС Windows|393297|  
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] установлена в Windows 10|394254|  
    |Платформа [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], установленная во всех остальных версиях ОС Windows|394271|  
  
     Далее приводится пример проверки на наличие значения, большего или равного значениям ключевого слова выпуска для каждой версии.  
  
     [!code-csharp[ListVersions#0](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#0)]
     [!code-vb[ListVersions#0](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#0)]  
    [!code-csharp[ListVersions#3](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#3)]
    [!code-vb[ListVersions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#3)]  
    [!code-csharp[ListVersions#4](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#4)]
    [!code-vb[ListVersions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#4)]  
  
     Выходные данные этого примера выглядят примерно следующим образом:  
  
    ```  
    Version: 4.5.1 or later  
    ```  
  
<a name="clr_a"></a>   
#### Поиск текущей версии среды выполнения с помощью средства Clrver  
  
-   Для определения версий среды CLR, установленных на компьютере, можно использовать инструмент CLR Version \(Clrver.exe\).  
  
     В командной строке Visual Studio введите `clrver`. Выходные данные этой команды выглядят примерно следующим образом:  
  
    ```  
    Versions installed on the machine: v2.0.50727 v4.0.30319  
    ```  
  
     Дополнительные сведения об использовании этого инструмента см. в разделе [Clrver.exe \(CLR Version Tool\)](../../../docs/framework/tools/clrver-exe-clr-version-tool.md).  
  
<a name="clr_b"></a>   
#### Поиск текущей версии среды выполнения путем запроса класса Environment в коде  
  
-   Запросите извлекаемое свойство <xref:System.Environment.Version%2A?displayProperty=fullName>, чтобы получить объект <xref:System.Version>, определяющий версию среды выполнения, в которой в данный момент выполняется код. Можно использовать свойство <xref:System.Version.Major%2A?displayProperty=fullName>, чтобы получить идентификатор основного выпуска \(например, "4" в случае версии 4,0\), свойство <xref:System.Version.Minor%2A?displayProperty=fullName>, чтобы получить идентификатор дополнительного номера версии \(например, "0" в случае версии 4,0\), либо метод <xref:System.Object.ToString%2A?displayProperty=fullName>, чтобы получить всю строку версии \(например, "4.0.30319.18010", как показано в следующем коде\). Это свойство возвращает одно значение, отражающее версию среды выполнения, в которой в данный момент выполняется код; оно не возвращает версии сборок или другие версии среды выполнения, которые могут быть установлены на компьютере.  
  
     Для платформы .NET Framework версий 4, 4.5, 4.5.1 и 4.5.2 свойство <xref:System.Environment.Version%2A?displayProperty=fullName> возвращает объект <xref:System.Version>, строковое представление которого имеет форму `4.0.30319.xxxxx`. Для [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] представление имеет форму `4.0.30319.42000`.  
  
     Ниже приведен пример запроса свойства <xref:System.Environment.Version%2A?displayProperty=fullName> для получения сведений о версии среды выполнения:  
  
     [!code-csharp[ListVersions#0](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#0)]
     [!code-vb[ListVersions#0](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#0)]  
    [!code-csharp[ListVersions#2](../../../samples/snippets/csharp/VS_Snippets_CLR/listversions/cs/program.cs#2)]
    [!code-vb[ListVersions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listversions/vb/program.vb#2)]  
  
     Выходные данные этого примера выглядят примерно следующим образом:  
  
    ```  
    Version: 4.0.30319.18010  
    ```  
  
## См. также  
 [Практическое руководство.Определение установленных обновлений платформы .NET Framework](../../../docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)   
 [Руководство по установке](../../../docs/framework/install/guide-for-developers.md)   
 [Версии и зависимости](../../../docs/framework/migration-guide/versions-and-dependencies.md)