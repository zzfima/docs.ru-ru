---
title: Как выполнить  Определение установленных версий платформы .NET Framework
ms.date: 02/20/2019
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
ms.openlocfilehash: d7661b3ebaa8f29d6d3b2adbc56c405c8f0945f3
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584178"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Как выполнить  Определение установленных версий платформы .NET Framework

На компьютере можно установить и запустить несколько версий платформы .NET Framework. При разработке или развертывании приложения могут потребоваться сведения о том, какие версии .NET Framework установлены на компьютере пользователя. Учтите, что платформа .NET Framework состоит из основных компонентов, версии которым присваиваются отдельно:  
  
- набор сборок, которые являются коллекциями типов и ресурсов, обеспечивающих функции приложений (.NET Framework и сборкам назначается один номер версии);  
  
- среда CLR, которая выполняет код приложения и управляет им. CLR имеет собственный номер версии (см. раздел [Версии и зависимости .NET Framework](~/docs/framework/migration-guide/versions-and-dependencies.md)).  
  
Чтобы получить точный список версий .NET Framework, установленных на компьютере, можно просмотреть реестр или отправить запрос в реестр с помощью кода:  
  
 [Поиск в реестре .NET Framework версий 1–4](#net_a)  
 [Поиск в реестре .NET Framework 4.5 и более поздних версий](#net_b)  
 [Использование кода для отправки запроса в реестр (версии 1–4)](#net_c)  
 [Использование кода для отправки запроса в реестр (версия 4.5 и более поздние)](#net_d)  
 [Использование PowerShell для отправки запроса в реестр (версия 4.5 и более поздние)](#ps_a)  

 Чтобы узнать версию среды CLR, можно использовать специальное средство или код:  
  
 [Использование средства Clrver](#clr_a)  
 [Использование кода для отправки запроса в класс System.Environment](#clr_b)  

> [!NOTE]
> Существует разница между версией .NET Framework и версией общеязыковой среды выполнения (CLR). Версия .NET Framework зависит от набора сборок, которые образуют библиотеку классов .NET Framework. Например, версии .NET Framework включают в себя 4.5, 4.6.1 и 4.7.2. Версия среды CLR зависит от среды выполнения, в которой выполняются приложения .NET Framework, где одна версия среды CLR обычно поддерживает несколько версий .NET Framework. CLR версии 4.30319.*xxxxx* поддерживает .NET Framework версии с 4 по 4.5.2, а среда CLR версии 4.30319.42000 поддерживает .NET Framework, начиная с версии 4.6. Дополнительные сведения см. в описании свойства <xref:System.Environment.Version?displayProperty=nameWithType>.

 Сведения об определении установленных обновлений для каждой версии платформы .NET Framework см. в статье [Практическое руководство. Определение установленных обновлений и исправлений безопасности платформы .NET Framework](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md). Сведения об установке .NET Framework см. в разделе [Установка .NET Framework для разработчиков](../../../docs/framework/install/guide-for-developers.md).  
  
<a name="net_a"></a>   
## <a name="find-net-framework-versions-1-4-in-the-registry"></a>Поиск в реестре .NET Framework версий 1–4 
  
1.  В меню **Пуск** выберите **Выполнить**.  
  
2.  В поле **Открыть** введите **regedit.exe**.  
  
     Для запуска regedit.exe необходимы учетные данные администратора.  
  
3.  В редакторе реестра откройте следующий подраздел:  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     Установленные версии .NET Framework с 1.1 по 3.5 перечислены как подразделы в подразделе `NDP`. Номер версии хранится в записи **Version** подраздела версий. 
     
     Для .NET Framework 4 запись **Version** находится в подразделе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client` или `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full` либо в обоих подразделах.

    > [!NOTE]
    > Папка NET Framework Setup в реестре не начинается с точки.

    На следующем рисунке показан подраздел .NET Framework 3.5 вместе с записью **Version**.

     ![Запись реестра для .NET Framework 3.5](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET Framework 4 и более ранних версий")

<a name="net_b"></a> 
## <a name="find-net-framework-versions-45-and-later-in-the-registry"></a>Поиск в реестре .NET Framework версии 4.5 и более поздних версий

1. В меню **Пуск** выберите **Выполнить**.

2. В поле **Открыть** введите **regedit.exe**.

     Для запуска regedit.exe необходимы учетные данные администратора.

3. В редакторе реестра откройте следующий подраздел:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     Обратите внимание, что путь к подразделу `Full` включает подраздел `Net Framework` вместо `.NET Framework`.

    > [!NOTE]
    > Если подраздел `Full` отсутствует, платформа .NET Framework 4.5 или более поздней версии не установлена.

     Проверьте значение DWORD с именем `Release`. Наличие значения DWORD `Release` указывает, что на компьютере установлена платформа .NET Framework 4.5 или более поздней версии. Это значение является разделом выпуска, который соответствует определенной версии .NET Framework. Например, на следующем рисунке значение параметра DWORD `Release` равно 378389, что является разделом выпуска для .NET Framework 4.5. 

     ![Запись реестра для .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")

В следующей таблице перечислены минимальные значения параметра DWORD `Release` для каждой версии .NET Framework. Эти значения можно использовать следующим образом:

- Чтобы определить наличие минимальной версии .NET Framework, проверьте, является ли значение DWORD `Release`, найденное в реестре, *большим* значения, указанного в таблице, или равным ему. Например, если приложению требуется .NET Framework 4.7 или более поздней версии, необходимо проверить на наличие минимального значения раздела выпуска 460798.

- Чтобы протестировать на наличие нескольких версий, начните с последней версии .NET Framework, а затем протестируйте на каждую последующую более раннюю версию.

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

|Версия платформы .NET Framework|Значение DWORD "Release"|
|--------------------------------|-------------|
|.NET Framework 4,5|378389|
|.NET Framework 4.5.1|378675|
|.NET Framework 4.5.2|379893|
|.NET Framework 4.6|393295|
|.NET Framework 4.6.1|394254|
|.NET Framework 4.6.2|394802|
|.NET Framework 4.7|460798|
|.NET Framework 4.7.1|461308|
|.NET Framework 4.7.2|461808|

Полную таблицу разделов выпуска .NET Framework для определенных версий операционной системы Windows см. в статье [Разделы выпуска .NET Framework и версии операционной системы Windows](release-keys-and-os-versions.md).

<a name="net_c"></a> 
## <a name="find-net-framework-versions-1-4-with-code"></a>Поиск в реестре .NET Framework версий 1–4 с помощью кода

- Используйте класс <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType>, чтобы получить доступ к подразделу `Software\Microsoft\NET Framework Setup\NDP\` в ветви `HKEY_LOCAL_MACHINE` реестра Windows.

     В следующем коде показан пример этого запроса.

    > [!NOTE]
    > Этот код не показывает, как обнаружить .NET Framework 4.5 или более поздней версии. Для обнаружения этих версий проверьте DWORD `Release`, как описано в предыдущем разделе. Для кода, обнаруживающего .NET Framework 4.5 или более поздние версии, см. следующий раздел в данной статье.

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

<a name="net_d"></a> 
## <a name="find-net-framework-versions-45-and-later-with-code"></a>Поиск в реестре .NET Framework 4.5 и более поздних версий с помощью кода

1. Наличие значения DWORD `Release` в разделе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` указывает на то, что среда .NET Framework 4.5 или более поздней версии установлена на компьютере. Значение ключевого слова указывает на установленную версию. Чтобы проверить это ключевое слово, используйте методы <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> и <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> для доступа к подразделу реестра Windows.

2. Проверьте значение ключевого слова `Release`, чтобы определить установленную версию. Чтобы обеспечить совместимость с будущими версиями, значение должно быть больше или равно значению, указанному в таблице в разделе [Поиск в реестре .NET Framework версии 4.5 и более поздних версии](#net_b).

В следующем примере в реестре проверяется значение `Release`, чтобы определить, установлена ли версия 4.5 или более поздняя версия .NET Framework.

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

В этом примере применяются рекомендации для проверки версии:

- Проверяется, имеет ли запись `Release` значение, *большее или равное* значению известных разделов выпуска.

- Проверка выполняется с самой последней до самой ранней версии.

<a name="ps_a"></a> 
## <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a>Проверка наличия минимально необходимой версии .NET Framework (4.5 и более поздней версии) с помощью PowerShell

В следующем примере проверяется значение ключевого слова `Release`, чтобы определить, установлена ли .NET Framework версии 4.6.2 или выше (`True` или `False`, если нет).

    ```PowerShell
    # PowerShell 5
    Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' | Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
    ```

    ```PowerShell
    # PowerShell 4
    (Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
    ```

    You can replace `394802` in the previous example with another value from the following table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section to check for a different minimum required .NET Framework version.
  
<a name="clr_a"></a> 
## <a name="find-the-current-clr-version-with-clrverexe"></a>Поиск текущей версии среды CLR с помощью Clrver.exe

Для определения версий среды CLR, установленных на компьютере, можно использовать инструмент CLR Version (Clrver.exe).

Запустите командную строку разработчика Visual Studio и введите `clrver`. Выходные данные этой команды выглядят примерно следующим образом:

```console
Versions installed on the machine:
v2.0.50727
v4.0.30319
```

Дополнительные сведения об использовании этого инструмента см. в разделе [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).

<a name="clr_b"></a> 
## <a name="find-the-current-clr-version-with-the-environment-class"></a>Поиск текущей версии среды CLR с помощью класса Environment

Можно извлечь значение свойства <xref:System.Environment.Version?displayProperty=nameWithType>, чтобы получить объект <xref:System.Version>, определяющий версию среды выполнения, в которой в данный момент выполняется код. Это свойство возвращает одно значение, отражающее версию среды выполнения, в которой в данный момент выполняется код. Оно не возвращает версии сборок или другие версии среды выполнения, которые могут быть установлены на компьютере. Можно использовать свойство <xref:System.Version.Major%2A?displayProperty=nameWithType>, чтобы получить идентификатор основного выпуска (например, "4" в случае версии 4.0), свойство <xref:System.Version.Minor%2A?displayProperty=nameWithType>, чтобы получить идентификатор дополнительной версии (например, "0" в случае версии 4.0), либо метод <xref:System.Version.ToString%2A?displayProperty=nameWithType>, чтобы получить всю строку версии (например, "4.0.30319.18010", как показано в следующем коде). 

Для платформы .NET Framework версий 4, 4.5, 4.5.1 и 4.5.2 свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> возвращает объект <xref:System.Version>, строковое представление которого имеет форму `4.0.30319.xxxxx`. Для .NET Framework 4.6 и более поздних версий оно имеет форму `4.0.30319.42000`.

> [!IMPORTANT]
> Для .NET Framework 4.5 и более поздней версии не рекомендуется использовать свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType>, чтобы определить версии среды выполнения. Вместо этого рекомендуется отправить запрос в реестр, как описано в разделе [Поиск версий .NET Framework путем отправки запроса в реестр (.NET Framework 4.5 и более поздних версий)](#net_d) выше в этой статье.

В следующем примере свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> используется для получения сведений о версии среды выполнения:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>См. также

- [Практическое руководство. Определение установленных обновлений и исправлений безопасности платформы .NET Framework](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)
- [Установка .NET Framework для разработчиков](../../../docs/framework/install/guide-for-developers.md)
- [Версии и зависимости](~/docs/framework/migration-guide/versions-and-dependencies.md)
