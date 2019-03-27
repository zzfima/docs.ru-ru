---
title: Практическое руководство. Определение установленных версий платформы .NET Framework
ms.date: 03/18/2019
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
ms.openlocfilehash: 8b7c7704c4f417ef16d3a79fa6d955265e42cf14
ms.sourcegitcommit: e994e47d3582bf09ae487ecbd53c0dac30aebaf7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2019
ms.locfileid: "58262442"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Практическое руководство. Определение установленных версий платформы .NET Framework

На компьютере можно [установить](https://docs.microsoft.com/dotnet/framework/install) и запустить несколько версий платформы .NET Framework. При разработке или развертывании приложения могут потребоваться сведения о том, какие версии .NET Framework установлены на компьютере пользователя. 

Платформа .NET Framework состоит из двух основных компонентов, версии которым присваиваются отдельно:  
  
- набор сборок, которые являются коллекциями типов и ресурсов, обеспечивающих функции приложений (.NET Framework и сборкам назначается один номер версии);  
  
- среда CLR, которая выполняет код приложения и управляет им. CLR имеет собственный номер версии (см. раздел [Версии и зависимости .NET Framework](~/docs/framework/migration-guide/versions-and-dependencies.md)).  

> [!NOTE]
> В каждой новой версии платформы .NET Framework сохранены функции предыдущих версий и добавлены новые функции. Можно загружать несколько версий платформы .NET Framework на одном компьютере одновременно. Это значит, что можно установить платформу .NET Framework, не удаляя предыдущие версии. Обычно не рекомендуется удалять предыдущие версии .NET Framework, так как используемое приложение может зависеть от конкретной версии .NET Framework и удаление платформы приведет к сбою в его работе.
>
> Существует разница между версией .NET Framework и версией общеязыковой среды выполнения (CLR). 
> - Версия .NET Framework зависит от набора сборок, которые образуют библиотеку классов .NET Framework. Например, версии .NET Framework включают в себя 4.5, 4.6.1 и 4.7.2. 
>- Версия среды CLR зависит от среды выполнения, в которой выполняются приложения .NET Framework. Одна версия среды CLR обычно поддерживает несколько версий .NET Framework. Например, среда CLR версии 4.0.30319.*xxxxx* поддерживает .NET Framework версии с 4 по 4.5.2, а среда CLR версии 4.0.30319.42000 поддерживает .NET Framework начиная с версии 4.6. 
>
> Дополнительные сведения о версиях см. в статье [Версии и зависимости платформы .NET Framework](versions-and-dependencies.md).


Получить список версий .NET Framework, установленных на компьютере, можно из реестра. Вы можете просмотреть реестр в редакторе реестра или отправить запрос с помощью кода.
 
- Поиск .NET Framework 4.5 и более поздних версий: 
     - [Поиск версий .NET Framework с помощью редактора реестра](#net_b)  
     - [Запрос версий .NET Framework из реестра с помощью кода](#net_d)  
     - [Запрос версий .NET Framework из реестра с помощью PowerShell](#ps_a)
 - Поиск более ранних версий .NET Framework (1–4):
     - [Поиск версий .NET Framework с помощью редактора реестра](#net_a)
     - [Запрос версий .NET Framework из реестра с помощью кода](#net_c)   

Получить список версий среды CLR, установленных на компьютере, можно с помощью специального средства или кода.  
  
 - [Использование средства Clrver](#clr_a)  
 - [Использование кода для отправки запроса в класс Environment](#clr_b)  

Сведения об определении установленных обновлений для каждой версии платформы .NET Framework см. в статье [Практическое руководство. Определение установленных обновлений платформы .NET Framework](how-to-determine-which-net-framework-updates-are-installed.md). 
  

## <a name="find-newer-net-framework-versions-45-and-later"></a>Поиск .NET Framework 4.5 и более поздних версий

<a name="net_b"></a> 
### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a>Поиск в реестре .NET Framework версии 4.5 и более поздних версий

1. В меню **Пуск** выберите **Выполнить**, введите *regedit* и нажмите кнопку **ОК**.

     Для запуска программы regedit необходимы учетные данные администратора.

2. В редакторе реестра откройте следующий подраздел: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**. Если подраздел **Full** отсутствует, платформа .NET Framework 4.5 или более поздней версии не установлена.

    > [!NOTE]
    > Папка **NET Framework Setup** в реестре не начинается с точки.

3. Проверьте значение DWORD с именем **Release**. Если оно имеется, платформа .NET Framework 4.5 или более поздней версии установлена. Это значение является разделом выпуска, который соответствует определенной версии .NET Framework. Например, на приведенном ниже рисунке значение параметра **Release** равно *378389*, что является разделом выпуска для .NET Framework 4.5. 

     ![Запись реестра для .NET Framework 4.5](media/clr-installdir.png "Запись реестра для .NET Framework 4.5")

В приведенной ниже таблице перечислены минимальные значения параметра **Release** для каждой версии .NET Framework. Эти значения можно использовать следующим образом:

- Чтобы определить наличие минимальной версии .NET Framework, проверьте, является ли значение **Release** типа DWORD, найденное в реестре, *большим* значения, указанного в таблице, или равным ему. Например, если приложению требуется .NET Framework 4.7 или более поздней версии, необходимо проверить наличие минимального значения раздела выпуска *460798*.

- Чтобы протестировать на наличие нескольких версий, начните с последней версии .NET Framework, а затем протестируйте на каждую последующую более раннюю версию.

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

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


<a name="net_d"></a> 
### <a name="find-net-framework-versions-45-and-later-with-code"></a>Поиск в реестре .NET Framework 4.5 и более поздних версий с помощью кода

1. Используйте методы <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> и <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> для доступа к подразделу **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** в реестре Windows.

    Наличие параметра **Release** типа DWORD в подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** свидетельствует о том, что на компьютере установлена платформа .NET Framework 4.5 или более поздней версии. 

2. Проверьте значение параметра **Release**, чтобы определить установленную версию. Для обеспечения совместимости с последующими версиями значение должно быть больше или равно значению, указанному в [таблице версий .NET Framework](#version_table).

В следующем примере проверяется значение **Release** в реестре для поиска установленной версии .NET Framework 4.5 или более поздних.

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

В этом примере применяются рекомендации для проверки версии:

- Проверяется, имеет ли параметр **Release** значение, *большее или равное* значению известных разделов выпуска.

- Проверка выполняется с самой последней до самой ранней версии.

<a name="ps_a"></a> 
### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a>Проверка наличия минимально необходимой версии .NET Framework (4.5 или более поздней) с помощью PowerShell

- Используйте команды PowerShell для проверки значения параметра **Release** в подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.

В приведенных ниже примерах значение **Release** проверяется с целью определить, установлена ли версия 4.6.2 или более поздняя версия .NET Framework. Код возвращает значение `True`, если одна из таких версий установлена, и `False` в противном случае.

```PowerShell
# PowerShell 5
 Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' |  Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
 ```

```PowerShell
# PowerShell 4
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
```

Чтобы проверить наличие другой минимальной необходимой версии .NET Framework, замените значение *394802* в этих примерах на значение **Release** из [таблицы версий NET Framework](#version_table).

## <a name="find-older-net-framework-versions-182114"></a>Поиск более ранних версий .NET Framework (1–4)

<a name="net_a"></a>
### <a name="find-net-framework-versions-182114-in-the-registry"></a>Поиск в реестре .NET Framework версий 1–4 
  
1. В меню **Пуск** выберите **Выполнить**, введите *regedit* и нажмите кнопку **ОК**.
  
    Для запуска программы regedit необходимы учетные данные администратора.  

2. В редакторе реестра откройте следующий подраздел: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**.  

    - Каждая установленная версия .NET Framework с 1.1 по 3.5 указывается как отдельный подраздел в разделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**. Пример: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**. Номер версии хранится в параметре **Version** подраздела версии. 
     
    - Для версии .NET Framework 4 параметр **Version** находится в подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client**, подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** или в обоих этих подразделах.

    > [!NOTE]
    > Папка **NET Framework Setup** в реестре не начинается с точки.

    На приведенном ниже рисунке показан подраздел для версии .NET Framework 3.5 вместе с параметром **Version**.

    ![Запись реестра для .NET Framework 3.5](media/net-4-and-earlier.png ".NET Framework 3.5 и более ранних версий")

<a name="net_c"></a> 
### <a name="find-net-framework-versions-182114-with-code"></a>Поиск .NET Framework версий 1–4 с помощью кода

- Используйте класс <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> для доступа к подразделу **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** в реестре Windows.

В следующем примере ищутся установленные версии .NET Framework 1–4:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]


## <a name="find-clr-versions"></a>Поиск версий CLR
  
<a name="clr_a"></a> 
### <a name="find-the-current-clr-version-with-clrverexe"></a>Поиск текущей версии среды CLR с помощью Clrver.exe

Для определения версий среды CLR, установленных на компьютере, можно использовать [средство CLR Version (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md).

- Запустите [Командную строку разработчика для Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) и введите `clrver`.

    Пример полученных результатов:

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a> 
### <a name="find-the-current-clr-version-with-the-environment-class"></a>Поиск текущей версии среды CLR с помощью класса Environment

> [!IMPORTANT]
> Для .NET Framework 4.5 и более поздних версий не следует использовать свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> для определения версии среды CLR. Вместо этого выполните запрос к реестру, как описано в разделе [Поиск .NET Framework версии 4.5 и более поздних с помощью кода](#net_d).

1. Выполните запрос к свойству <xref:System.Environment.Version?displayProperty=nameWithType>, чтобы получить объект <xref:System.Version>. 

    Возвращенный объект `System.Version` указывает версию среды выполнения, в которой в настоящее время выполняется код. Он не содержит версий сборок или других версий среды выполнения, которые установлены на компьютере.

    Для платформы .NET Framework версий 4, 4.5, 4.5.1 и 4.5.2 возвращаемый объект <xref:System.Version> имеет строковое представление 4.0.30319.*xxxxx*. Для .NET Framework 4.6 и более поздних версий оно имеет форму 4.0.30319.42000.    

2. Получив объект `Version`, выполните к нему запрос.

   - Чтобы получить идентификатор основного выпуска (например, *4* в случае версии 4.0), используйте свойство <xref:System.Version.Major%2A?displayProperty=nameWithType>.

   - Чтобы получить идентификатор дополнительной версии (например, *0* в случае версии 4.0), используйте свойство <xref:System.Version.Minor%2A?displayProperty=nameWithType>.

   - Чтобы получить всю строку версии (например, *4.0.30319.18010*), используйте метод <xref:System.Version.ToString%2A?displayProperty=nameWithType>. Он возвращает одно значение, соответствующее версии среды выполнения, в которой выполняется код. Он не возвращает версий сборок или других версий среды выполнения, которые установлены на компьютере.



В следующем примере свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> используется для получения сведений о версии среды CLR:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>См. также

- [Практическое руководство. Определение установленных обновлений платформы .NET Framework](how-to-determine-which-net-framework-updates-are-installed.md)
- [Установка .NET Framework для разработчиков](../install/guide-for-developers.md)
- [Версии и зависимости платформы .NET Framework](versions-and-dependencies.md)
