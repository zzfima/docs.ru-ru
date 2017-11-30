---
title: "Практическое руководство. Определение установленных версий платформы .NET Framework"
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: edd5a8e8cc32037d45d95d544f6eae5097d0c468
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Практическое руководство.Определение установленных версий платформы .NET Framework
На компьютере можно установить и запустить несколько версий платформы .NET Framework. При разработке или развертывании приложения могут потребоваться сведения о том, какие версии .NET Framework установлены на компьютере пользователя. Учтите, что платформа .NET Framework состоит из основных компонентов, версии которым присваиваются отдельно:  
  
-   набор сборок, которые являются коллекциями типов и ресурсов, обеспечивающих функции приложений (.NET Framework и сборкам назначается один номер версии);  
  
-   среда CLR, которая выполняет код приложения и управляет им. CLR имеет собственный номер версии (см. раздел [Версии и зависимости .NET Framework](~/docs/framework/migration-guide/versions-and-dependencies.md)).  
  
 Чтобы получить точный список версий .NET Framework, установленных на компьютере, можно просмотреть реестр или отправить запрос в реестр с помощью кода:  
  
 [Просмотр реестра (версии 1–4)](#net_a)  
 [Просмотр реестра (версия 4.5 и более поздние)](#net_b)  
 [Использование кода для отправки запроса в реестр (версии 1–4)](#net_c)  
 [Использование кода для отправки запроса в реестр (версия 4.5 и более поздние)](#net_d)  
 [Использование PowerShell для отправки запроса в реестр (версия 4.5 и более поздние)](#ps_a)  
  
 Чтобы узнать версию среды CLR, можно использовать специальное средство или код:  
  
 [Использование средства Clrver](#clr_a)  
 [Использование кода для отправки запроса в класс System.Environment](#clr_b)  
  
 Сведения об обнаружении установленных обновлений для каждой версии платформы .NET Framework см. в разделе [Практическое руководство. Определение установленных платформ .NET Framework](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md). Сведения об установке .NET Framework см. в разделе [Установка .NET Framework для разработчиков](../../../docs/framework/install/guide-for-developers.md).  
  
<a name="net_a"></a>   
#### <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-1-4"></a>Поиск версий .NET Framework путем просмотра реестра (.NET Framework 1–4)  
  
1.  В меню **Пуск** выберите **Выполнить**.  
  
2.  В поле **Открыть** введите **regedit.exe**.  
  
     Для запуска regedit.exe необходимы учетные данные администратора.  
  
3.  В редакторе реестра откройте следующий подраздел:  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     Установленные версии перечислены в подразделе NDP. Номер версии хранится в записи **Version**. Для [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] запись **Version** находится в подразделе Client или Full (внутри подраздела NDP) либо в обоих подразделах.  
  

    > [!NOTE]
    > Папка NET Framework Setup в реестре не начинается с точки.

<a name="net_b"></a> 
#### <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-45-and-later"></a>Поиск версий .NET Framework путем просмотра реестра (.NET Framework 4.5 и более поздних версий)

1. В меню **Пуск** выберите **Выполнить**.

2. В поле **Открыть** введите **regedit.exe**.

     Для запуска regedit.exe необходимы учетные данные администратора.

3. В редакторе реестра откройте следующий подраздел:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     Обратите внимание, что путь к подразделу `Full` включает подраздел `Net Framework` вместо `.NET Framework`.

    > [!NOTE]
    > Если подраздел `Full` отсутствует, платформа .NET Framework 4.5 или более поздней версии не установлена.

     Проверьте значение DWORD с именем `Release`. Наличие DWORD `Release` указывает, что на компьютере установлена [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более новая версия.

     ![Запись реестра для .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")

     Значение DWORD `Release` показывает, какая версия .NET Framework установлена.

    |Значение DWORD "Release"|Версия|
    |--------------------------------|-------------|
    |378389|.NET Framework 4,5|
    |378675|Платформа .NET Framework 4.5.1, установленная с Windows 8.1 или Windows Server 2012 R2|
    |378758|Платформа .NET Framework 4.5.1, установленная в Windows 8, Windows 7 с пакетом обновления 1 (SP1) или Windows Vista с пакетом обновления 2 (SP2)|
    |379893|.NET Framework 4.5.2|
    |В системах Windows 10: 393295<br /><br /> Во всех других версиях ОС: 393297|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|
    |В системах Windows 10 с ноябрьским обновлением: 394254<br /><br /> Во всех других версиях ОС: 394271|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|
    |В юбилейном обновлении Windows 10 Anniversary Update: 394802<br /><br /> Во всех других версиях ОС: 394806|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]| 
    |В обновлении Windows 10 Creators Update: 460798<br/><br/> Во всех других версиях ОС: 460805 | .NET Framework 4.7 |
    |В Windows 10 попадают создатели обновления: 461308<br/><br/> Во всех остальных версиях ОС: 461310 | .NET framework 4.7.1 |
<a name="net_c"></a> 
#### <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-1-4"></a>Поиск версий .NET Framework путем отправки запроса в реестр (.NET Framework 1–4)

- Используйте класс <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> для доступа к подразделу Software\Microsoft\NET Framework Setup\NDP\ в разделе HKEY_LOCAL_MACHINE в реестре Windows.

     В следующем коде показан пример этого запроса.

    > [!NOTE]
    > В этом коде не показано, как обнаружить платформу [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более поздней версии. Для обнаружения этих версий проверьте DWORD `Release`, как описано в предыдущем разделе. Для кода, обнаруживающего [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более поздние версии, см. следующий раздел в данной статье.

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

     Выходные данные этого примера выглядят примерно следующим образом:

    ```
    v2.0.50727  2.0.50727.4016  SP2
    v3.0  3.0.30729.4037  SP2
    v3.5  3.5.30729.01  SP1
    v4
      Client  4.0.30319
      Full  4.0.30319
    ```

<a name="net_d"></a> 
#### <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-45-and-later"></a>Поиск версий .NET Framework путем отправки запроса в реестр (.NET Framework 4.5 и более поздних версий)

1. Наличие значения DWORD `Release` указывает, что на компьютере установлена платформа .NET Framework 4.5 или более поздней версии. Значение ключевого слова указывает на установленную версию. Чтобы проверить это ключевое слово, используйте методы <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> и <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> класса <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> для доступа к подразделу Software\Microsoft\NET Framework Setup\NDP\v4\Full в разделе HKEY_LOCAL_MACHINE реестра Windows.

2. Проверьте значение ключевого слова `Release`, чтобы определить установленную версию. Для обеспечения совместимости с последующими версиями значение должно быть больше или равно значениям, указанным в таблице. Ниже приведен список версий .NET Framework и соответствующих ключевых слов `Release`.

    |Версия|Значение DWORD "Release"|
    |-------------|--------------------------------|
    |.NET Framework 4,5|378389|
    |Платформа .NET Framework 4.5.1, установленная с Windows 8.1|378675|
    |Платформа .NET Framework 4.5.1, установленная в Windows 8, Windows 7 с пакетом обновления 1 (SP1) или Windows Vista с пакетом обновления 2 (SP2)|378758|
    |.NET Framework 4.5.2|379893|
    |Платформа [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], установленная с Windows 10|393295|
    |Платформа [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], установленная во всех остальных версиях ОС Windows|393297|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] установлена в Windows 10|394254|
    |Платформа [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], установленная во всех остальных версиях ОС Windows|394271|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] установлена в юбилейном обновлении Windows 10 Anniversary Update|394802|
    |Платформа [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], установленная во всех остальных версиях ОС Windows|394806|
    |.NET Framework 4.7 установлена в обновлении Windows 10 Creators Update|460798|
    |Платформа .NET Framework 4.7, установленная во всех остальных версиях ОС Windows|460805|
    |.NET framework установлены в центре обновления Windows 10 Осень создатели 4.7.1|461308|
    |.NET framework установлены на всех остальных версиях ОС Windows 4.7.1|461310|

     В следующем примере проверяется значение `Release` в реестре, чтобы определить, установлена ли [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более поздняя версия .NET Framework.

     [!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
     [!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

     В этом примере применяются рекомендации для проверки версии:

    - Проверяется, имеет ли запись `Release` значение, *большее или равное* значению известных разделов выпуска.

    - Проверка выполняется с самой последней до самой ранней версии.

<a name="ps_a"></a> 
#### <a name="to-check-for-a-minimum-required-net-framework-version-by-querying-the-registry-in-powershell-net-framework-45-and-later"></a>Проверка минимальной необходимой версии .NET Framework путем запроса к реестру в PowerShell (.NET Framework 4.5 и более поздние версии)

- В приведенном ниже примере проверяется значение ключевого слова `Release` для определения того, установлена ли версия .NET Framework 4.6.2 или более поздняя, вне зависимости от версии Windows (если да, возвращается значение `True`; в противном случае возвращается значение `False`).

    ```PowerShell
    Get-ChildItem "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\" | Get-ItemPropertyValue -Name Release | ForEach-Object { $_ -ge 394802 } 
    ```

    Значение `394802` в предыдущем примере можно заменить на другое значение из приведенной ниже таблицы для проверки наличия другой версии .NET Framework.
  
    |Версия|Минимальное значение DWORD "Release"|
    |-------------|--------------------------------|
    |.NET Framework 4.5|378389|
    |.NET Framework 4.5.1|378675|
    |.NET Framework 4.5.2|379893|
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|393295|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|394254|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|394802|
    |.NET Framework 4.7|460798|
    |.NET framework 4.7.1|461308|
    
<a name="clr_a"></a> 
#### <a name="to-find-the-current-runtime-version-by-using-the-clrver-tool"></a>Поиск текущей версии среды выполнения с помощью средства Clrver

- Для определения версий среды CLR, установленных на компьютере, можно использовать инструмент CLR Version (Clrver.exe).

     В командной строке Visual Studio введите `clrver`. Выходные данные этой команды выглядят примерно следующим образом:

    ```
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

     Дополнительные сведения об использовании этого инструмента см. в разделе [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).

<a name="clr_b"></a> 
#### <a name="to-find-the-current-runtime-version-by-querying-the-environment-class-in-code"></a>Поиск текущей версии среды выполнения путем запроса класса Environment в коде

- Запросите извлекаемое свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType>, чтобы получить объект <xref:System.Version>, определяющий версию среды выполнения, в которой в данный момент выполняется код. Можно использовать свойство <xref:System.Version.Major%2A?displayProperty=nameWithType>, чтобы получить идентификатор основного выпуска (например, "4" в случае версии 4,0), свойство <xref:System.Version.Minor%2A?displayProperty=nameWithType>, чтобы получить идентификатор дополнительного номера версии (например, "0" в случае версии 4,0), либо метод <xref:System.Object.ToString%2A?displayProperty=nameWithType>, чтобы получить всю строку версии (например, "4.0.30319.18010", как показано в следующем коде). Это свойство возвращает одно значение, отражающее версию среды выполнения, в которой в данный момент выполняется код; оно не возвращает версии сборок или другие версии среды выполнения, которые могут быть установлены на компьютере.

     Для платформы .NET Framework версий 4, 4.5, 4.5.1 и 4.5.2 свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> возвращает объект <xref:System.Version>, строковое представление которого имеет форму `4.0.30319.xxxxx`. Для .NET Framework 4.6 и более поздних версий оно имеет форму `4.0.30319.42000`.

    > [!IMPORTANT]
    > Для [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] и более поздней версии не рекомендуется использовать свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> для определения версии среды выполнения. Вместо этого рекомендуется отправить запрос в реестр, как описано в разделе [Поиск версий .NET Framework путем отправки запроса в реестр (.NET Framework 4.5 и более поздних версий)](#net_d) выше в этой статье.

     Ниже приведен пример запроса свойства <xref:System.Environment.Version%2A?displayProperty=nameWithType> для получения сведений о версии среды выполнения:

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

     Выходные данные этого примера выглядят примерно следующим образом:

    ```
    Version: 4.0.30319.18010
    ```

## <a name="see-also"></a>См. также
 [Практическое руководство. Определение установленных обновлений платформы .NET Framework](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)  
 [Установите .NET Framework для разработчиков](../../../docs/framework/install/guide-for-developers.md)  
 [Версии и зависимости](~/docs/framework/migration-guide/versions-and-dependencies.md)
