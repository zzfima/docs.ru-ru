---
title: Версии .NET Framework и ОС Windows
ms.custom: updateeachrelease
ms.date: 01/17/2020
helpviewer_keywords:
- versions, .NET Framework
ms.assetid: f75a72de-e2f2-4a7a-9574-3f278684ea90
ms.openlocfilehash: 486b320ca30323684d301630ad29f8f4615764ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "77504059"
---
# <a name="net-framework-versions-and-dependencies"></a>Версии и зависимости платформы .NET Framework

В каждую версию платформы .NET Framework входит среда CLR, библиотеки базовых классов и другие управляемые библиотеки. В этой статье описаны основные особенности различных версий платформы .NET Framework, приведены сведения о базовых версиях среды CLR и соответствующих средах разработки, а также указаны версии, устанавливаемые системой Windows (ОС).

В каждой новой версии платформы .NET Framework добавлены новые функции и сохранены функции предыдущих версий.

Среда CLR определяется своим собственным номером версии. Номер версии платформы .NET Framework увеличивается при каждом выпуске, но версия среды CLR увеличивается не всегда. Например, в .NET Framework 4, 4.5 и более поздние выпуски входит среда CLR 4, а в .NET Framework 2.0, 3.0 и 3.5 — среда CLR 2.0. (Версии 3 среды CLR не было.)

> [!TIP]
>
> - Полный список поддерживаемых операционных систем см. в статье [Требования к системе для .NET Framework](../get-started/system-requirements.md).
> - Скачиваемые файлы см. в разделе [Установка .NET Framework для разработчиков](../install/guide-for-developers.md).
> - Сведения об определении установленных версий .NET Framework на компьютере см. [Практическое руководство. Определение установленных версий платформы .NET Framework](how-to-determine-which-versions-are-installed.md).

## <a name="version-information"></a>Сведения о версии

В следующей таблице приводится краткий обзор истории версий .NET Framework и сопоставление каждой версии с Visual Studio, Windows и Windows Server. Visual Studio поддерживает работу с различными версиями, поэтому вы не ограничены только указанной версией платформы .NET Framework.

- Значок галочки ✔️ обозначает версии ОС, на которых установлена .NET Framework и нужно ли ее включить [в панели управления](../install/dotnet-35-windows-10.md) (для Windows) или с помощью диспетчера сервера (для Windows Server).
- Значок знака плюс ➕ обозначает версии ОС, на которых .NET Framework предварительно не установлена, но может быть установлена.

| | |
| - | - |
| [.NET Framework 4.8](#net-framework-48) | [.NET Framework 4.7.2](#net-framework-472) | [.NET Framework 4.7.1](#net-framework-471) | [.NET Framework 4.7](#net-framework-47) |
| [.NET Framework 4.6.2](#net-framework-462) | [.NET Framework 4.6.1](#net-framework-461) | [.NET Framework 4.6](#net-framework-46) | [.NET Framework 4.5.2](#net-framework-452) |
| [.NET Framework 4.5.1](#net-framework-451) | [.NET Framework 4.5](#net-framework-45) | [.NET Framework 4](#net-framework-4) | [.NET Framework 3.5](#net-framework-35) |
| [.NET Framework 3.0](#net-framework-30) | [.NET Framework 2.0](#net-framework-20) | [.NET Framework 1.1](#net-framework-11) | [.NET Framework 1.0](#net-framework-10) |

### <a name="net-framework-48"></a>.NET Framework 4.8

- [Новые функции](../whats-new/index.md#whats-new-in-net-framework-48)
- [Новые специальные возможности](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-net-framework-48)
- [Заметки о выпуске](https://github.com/Microsoft/dotnet/tree/master/releases/net48/README.md)

|||
|-|-|
|**Версия среды CLR**|4|
|**Версии Windows**|✔️ 10, обновление за май 2019 г.<br/>➕ 10, обновление за октябрь 2018 г. (версия 1809)<br/>➕ 10, обновление за апрель 2018 г. (версия 1803)<br/>➕ 10 Fall Creators Update (версия 1709)<br/>➕ 10 Creators Update (версия 1703)<br/>➕ 10, юбилейное обновление (версия 1607)<br/>➕ 8.1<br/>➕7|
|**Версии Windows Server**|➕ Windows Server 2019<br/>➕ Windows Server, версия 1809<br/>➕ Windows Server, версия 1803<br/>➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 с пакетом обновления 1 (SP1)|
|**Определение установленной версии .NET**|Используйте DWORD `Release`:<br/>- 528040 (обновление Windows 10 за май 2019 г.)<br/>– 528049 (все остальные версии ОС)<br/>(См. [инструкции](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-472"></a>.NET Framework 4.7.2.

- [Новые функции](../whats-new/index.md#whats-new-in-net-framework-472)
- [Новые специальные возможности](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-net-framework-472)
- [Заметки о выпуске](https://github.com/Microsoft/dotnet/tree/master/releases/net472/README.md)

|||
|-|-|
|**Версия среды CLR**|4|
|**Включено в версию Visual Studio**|2019<sup>1</sup>|
|**Версии Windows**|✓ 10, обновление за октябрь 2018 г. (версия 1809)<br/>✓ 10, обновление за апрель 2018 г. (версия 1803)<br/>➕ 10 Fall Creators Update (версия 1709)<br/>➕ 10 Creators Update (версия 1703)<br/>➕ 10, юбилейное обновление (версия 1607)<br/>➕ 8.1<br/>➕7|
|**Версии Windows Server**|✔️ Windows Server 2019<br/>✔️ Windows Server, версия 1809<br/>✔️ Windows Server, версия 1803<br/>➕ Windows Server, версия 1709<br/>➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 с пакетом обновления 1 (SP1)|
|**Определение установленной версии .NET**|Используйте DWORD `Release`:<br/>– 461814 (обновление Windows 10 за октябрь 2018 г.)<br/>– 461808 (обновление Windows за 10 апреля 2018 г. и Windows Server, версия 1803)<br/>— 461814 (все остальные версии ОС)<br/>(См. [инструкции](how-to-determine-which-versions-are-installed.md))|

<sup>1</sup> — требуется установить **разработку классических приложений .NET**, **ASP.NET и веб-разработку**, **разработку Azure**, **разработку для Office или SharePoint**, **разработку мобильных приложений с помощью .NET**или рабочие нагрузки **Кроссплатформенная разработка .NET Core**.

### <a name="net-framework-471"></a>.NET Framework 4.7.1

- [Новые функции](../whats-new/index.md#whats-new-in-net-framework-471)
- [Новые специальные возможности](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-net-framework-471)
- [Заметки о выпуске](https://github.com/Microsoft/dotnet/tree/master/releases/net471/README.md)

|||
|-|-|
|**Версия среды CLR**|4|
|**Версии Windows**|✔️ 10 Fall Creators Update (версия 1709)<br/>➕ 10 Creators Update (версия 1703)<br/>➕ 10, юбилейное обновление (версия 1607)<br/>➕ 8.1<br/>➕7|
|**Версии Windows Server**|➕ Windows Server, версия 1803<br/>✔️ Windows Server, версия 1709<br/>➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 с пакетом обновления 1 (SP1)|
|**Определение установленной версии .NET**|Используйте DWORD `Release`:<br/>– 461308 (обновление Windows 10 Creators Update и Windows Server, версия 1709)<br/>— 461310 (все остальные версии ОС)<br/>(См. [инструкции](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-47"></a>.NET Framework 4.7

- [Новые функции](../whats-new/index.md#whats-new-in-net-framework-47)
- [Заметки о выпуске](https://github.com/Microsoft/dotnet/tree/master/releases/net47/README.md)

|||
|-|-|
|**Версия среды CLR**|4|
|**Версии Windows**|✔️ 10 Creators Update (версия 1703)<br/>➕ 10, юбилейное обновление (версия 1607)<br/>➕ 8.1<br/>➕7|
|**Версии Windows Server**|➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 с пакетом обновления 1 (SP1)|
|**Определение установленной версии .NET**|Используйте DWORD `Release`:<br/>– 460798 (обновление Windows 10 Creators Update)<br/>– 460805 (все другие версии ОС)<br/>(См. [инструкции](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-462"></a>.NET Framework 4.6.2

- [Новые функции](../whats-new/index.md#whats-new-in-net-framework-462)
- [Заметки о выпуске](https://github.com/Microsoft/dotnet/tree/master/releases/net462/README.md)

|||
|-|-|
|**Версия среды CLR**|4|
|**Версии Windows**|✔️ 10, юбилейное обновление (версия 1607)<br/>➕️ 10, ноябрьское обновление (версия 1511)<br/>➕ 10<br/>➕ 8.1<br />➕ 7|
|**Версии Windows Server**|✔️ 2016<br /><br/>➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 с пакетом обновления 1 (SP1)|
|**Определение установленной версии .NET**|Используйте DWORD `Release`:<br /><br/>– 394802 (юбилейное обновление Windows 10 и Windows Server 2016)<br/>– 394806 (все остальные версии ОС)<br /><br/>(См. [инструкции](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-461"></a>.NET Framework 4.6.1

- [Новые функции](../whats-new/index.md#whats-new-in-net-framework-461)
- [Заметки о выпуске](https://github.com/Microsoft/dotnet/tree/master/releases/net461/README.md)

|||
|-|-|
|**Версия среды CLR**|4|
|**Включено в версию Visual Studio**|2017<sup>1</sup>|
|**Версии Windows**|✔️ 10, ноябрьское обновление (версия 1511)<br/>➕ 10<br />➕ 8.1<br />➕ 8<br />➕ 7|
|**Версии Windows Server**|➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 с пакетом обновления 1 (SP1)|
|**Определение установленной версии .NET**|Используйте DWORD `Release`:<br /><br/>– 394254 (ноябрьское обновление Windows 10)<br />– 394271 (все остальные версии ОС)<br /><br/>(См. [инструкции](how-to-determine-which-versions-are-installed.md))|

<sup>1</sup> — требуется установить **разработку классических приложений .NET**, **ASP.NET и веб-разработку**, **разработку Azure**, **разработку для Office или SharePoint**, **разработку мобильных приложений с помощью .NET**или рабочие нагрузки **Кроссплатформенная разработка .NET Core**.

### <a name="net-framework-46"></a>.NET Framework 4.6

- [Новые функции](../whats-new/index.md#whats-new-in-net-2015)
- [Заметки о выпуске](https://github.com/Microsoft/dotnet/tree/master/releases/net46/README.md)

|||
|-|-|
|**Версия среды CLR**|4|
|**Включено в версию Visual Studio**|2015|
|**Версии Windows**|✔️ 10<br /><br />➕ 8.1<br />➕ 8<br />➕ 7<br />➕ Vista|
|**Версии Windows Server**|➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 с пакетом обновления 1 (SP1)<br />➕ 2008 SP2|
|**Определение установленной версии .NET**|Используйте DWORD `Release`:<br /><br />– 393295 (Windows 10)<br />– 393297 (все остальные версии ОС)<br /><br />(См. [инструкции](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-452"></a>.NET Framework 4.5.2

- [Новые функции](../whats-new/index.md#whats-new-in-net-framework-452)
- [Заметки о выпуске](https://github.com/Microsoft/dotnet/tree/master/releases/net452/README.md)

|||
|-|-|
|**Версия среды CLR**|4|
|**Версии Windows**|➕ 8.1<br />➕ 8<br />➕ 7<br />➕ Vista|
|**Версии Windows Server**|➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 с пакетом обновления 1 (SP1)<br />➕ 2008 SP2|
|**Определение установленной версии .NET**|Используйте DWORD 379893 `Release`<br /><br />(См. [инструкции](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-451"></a>.NET Framework 4.5.1

- [Новые функции](../whats-new/index.md#whats-new-in-net-framework-451)
- [Заметки о выпуске](https://github.com/Microsoft/dotnet/tree/master/releases/net451/README.md)

|||
|-|-|
|**Версия среды CLR**|4|
|**Включено в версию Visual Studio**|2013|
|**Версии Windows**|✔️ 8.1<br /><br />➕ 8<br />➕ 7<br />➕ Vista|
|**Версии Windows Server**|✔️ 2012 R2<br /><br />➕ 2012<br />➕ 2008 R2 с пакетом обновления 1 (SP1)<br />➕ 2008 SP2|
|**Определение установленной версии .NET**|Используйте DWORD `Release`:<br /><br />– 378675 (Windows 8.1)<br />– 378758 (все остальные)<br /><br />(См. [инструкции](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-45"></a>.NET Framework 4.5

- [Новые функции](../whats-new/index.md#whats-new-in-net-framework-45)
- [Заметки о выпуске](https://github.com/Microsoft/dotnet/tree/master/releases/net45/README.md)

|||
|-|-|
|**Версия среды CLR**|4|
|**Включено в версию Visual Studio**|2012|
|**Версии Windows**|✔️ 8<br />➕ 7<br />➕ Vista|
|**Версии Windows Server**|✔️ 2012<br />➕ 2008 R2 с пакетом обновления 1 (SP1)<br />➕ 2008 SP2|
|**Определение установленной версии .NET**|Используйте DWORD 378389 `Release`<br /><br />(См. [инструкции](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-4"></a>.NET Framework 4

[Новые функции](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms171868(v=vs.100))

|||
|-|-|
|**Версия среды CLR**|4|
|**Включено в версию Visual Studio**|2010|
|**Версии Windows**|➕ 7<br />➕ Vista|
|**Версии Windows Server**|➕ 2008 R2 с пакетом обновления 1 (SP1)<br />➕ 2008 SP2<br />➕ 2003|
|**Определение установленной версии .NET**|См. [инструкции](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-35"></a>.NET Framework 3,5

[Новые функции](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ms171868\(v=vs.90\)):

- LINQ
- Деревья выражений
- Улучшенная поддержка ASP.NET для разработки AJAX
- Коллекции HashSet
- DateTimeOffset
- Интеграция WPF и WF
- Одноранговая сеть
- Надстройки для расширяемости

|||
|-|-|
|**Версия среды CLR**|2.0|
|**Включено в версию Visual Studio**|2008|
|**Версии Windows**|✔️ 10\*<br/>✔️ 8.1\*<br />✔️ 8\*<br />✔️ 7<br /><br />➕ Vista|
|**Версии Windows Server**|➕ Windows Server, версия 1803\*<br/>➕ Windows Server, версия 1709\*<br/>➕ 2016\*<br/>➕ 2012 R2\*<br />➕ 2012\*<br /><br />✔️2008 R2 с пакетом обновления 1 (SP1)\*<br /><br/>➕ 2008 SP2<br />➕ 2003|
|**Определение установленной версии .NET**|См. [инструкции](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-30"></a>.NET Framework 3.0

[Новые функции](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb822048(v=vs.90)):

- Windows Presentation Foundation (WPF)
- Windows Communication Foundation
- Windows Workflow Foundation
- Windows CardSpace

|||
|-|-|
|**Версия среды CLR**|2.0|
|**Версии Windows**|✔️ Vista|
|**Версии Windows Server**|✔️ 2008 R2 с пакетом обновления 1 (SP1)*<br />✔️ 2008 SP2\*<br /><br />➕ 2003|
|**Определение установленной версии .NET**|Ознакомьтесь с [инструкциями](how-to-determine-which-versions-are-installed.md).|

### <a name="net-framework-20"></a>.NET Framework 2.0

[Новые функции](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t357fb32%28v%3dvs.90%29):

- Универсальные шаблоны
- Изменение и продолжение для отладчика
- Улучшенные масштабируемость и производительность
- развертывание ClickOnce
- Новые элементы управления и поддержка широкого спектра браузеров в ASP.NET 2.0
- поддержка 64–разрядной архитектуры

|||
|-|-|
|**Версия среды CLR**|2.0|
|**Включено в версию Visual Studio**|2005|
|**Версии Windows**|Недоступно|
|**Версии Windows Server**|✔️ 2008 R2 с пакетом обновления 1 (SP1)<br />✔️ 2008 SP2<br />✔️ 2003|
|**Определение установленной версии .NET**|См. [инструкции](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-11"></a>.NET Framework 1.1

[Новые функции](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/h88tthh0%28v%3dvs.90%29):

- Элементы управления ASP.NET для мобильных устройств
- Параллельное выполнение
- Поддержка протокола IPv6

|||
|-|-|
|**Версия среды CLR**|1,1|
|**Включено в версию Visual Studio**|2003|
|**Версии Windows**|Недоступно|
|**Версии Windows Server**|✔️ 2003|
|**Определение установленной версии .NET**|См. [инструкции](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-10"></a>.NET Framework 1.0

|||
|-|-|
|**Версия среды CLR**|1,0|
|**Включено в версию Visual Studio**|Visual Studio .NET|
|**Версии Windows**|Недоступно|
|**Версии Windows Server**|Недоступно|
|**Определение установленной версии .NET**|См. [инструкции](how-to-determine-which-versions-are-installed.md)|

> [!NOTE]
>
> - В этой операционной системе необходимо включить платформу .NET Framework с помощью [панели управления (для Windows) или диспетчера сервера (для Windows Server)](../install/dotnet-35-windows-10.md#enable-the-net-framework-35-in-control-panel).
> - Как правило, не требуется удалять какие-либо версии .NET Framework, уже установленные на вашем компьютере, потому что используемое приложение может зависеть от конкретной версии. В случае удаления какой-либо версии, исполнение может завершиться ошибкой. Можно загружать несколько версий платформы .NET Framework на одном компьютере одновременно. Это значит, что платформу .NET Framework можно установить, не удаляя предыдущие версии. Дополнительные сведения см. в разделе [Начало работы](../get-started/index.md).

## <a name="remarks-for-version-45-and-later"></a>Комментарии для версии 4.5 и более поздних версий

.NET Framework 4.5 — это обновление на месте, которое заменяет .NET Framework 4 на компьютере, и аналогично .NET Framework 4.5.1, 4.5.2, 4,6, 4.6.1, 4.6.2, 4,7, 4.7.1, 4.7.2 и 4.8 — это обновления на месте для .NET Framework 4.5. Обновление на месте означает, что они используют ту же версию среды выполнения, но версии сборок обновлены и включают новые типы и члены. После установки одного из этих обновлений приложения .NET Framework 4, .NET Framework 4.5, .NET Framework 4.6 или .NET Framework 4.7 должны продолжать работу без повторной компиляции. Однако обратное неверно. Не рекомендуется запускать приложения, предназначенные для более поздней версии .NET Framework, в более ранней версии. Например, не рекомендуется запускать приложение, предназначенное для .NET Framework 4.6, на .NET Framework 4.5.

Применяются следующие правила.

- В Visual Studio можно выбрать .NET Framework 4.5 в качестве целевой платформы для проекта (при этом задается свойство <xref:Microsoft.Build.Tasks.GetReferenceAssemblyPaths.TargetFrameworkMoniker%2A?displayProperty=nameWithType>), чтобы скомпилировать проект как сборку или исполняемый файл .NET Framework 4.5. Эту сборку или исполняемый файл можно использовать на любом компьютере, где установлена платформа .NET Framework 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 или 4.8.

- В Visual Studio можно выбрать .NET Framework 4.5.1 в качестве целевой платформы для проекта, чтобы скомпилировать проект как сборку или исполняемый файл .NET Framework 4.5.1. Запускайте эту сборку или исполняемый файл только на компьютерах, на которых установлен .NET Framework 4.5.1 или более поздней версии. Исполняемый файл с целевой платформой .NET Framework 4.5.1 будет заблокирован для выполнения на компьютере, где установлена только более ранняя версия .NET Framework, например .NET Framework 4.5. Пользователю будет предложено установить платформу .NET Framework 4.5.1. Кроме того, сборки .NET Framework 4.5.1 не должны вызываться из приложения, предназначенного для более ранней версии .NET Framework, такой как .NET Framework 4.5.

  > [!NOTE]
  > Платформы .NET Framework 4.5.1 и .NET Framework 4.5 используются здесь только в качестве примеров. Этот принцип применяется к любому приложению, предназначенному для более поздней версии .NET Framework, чем установленная в системе, в которой оно выполняется.

Некоторые обновления в платформе .NET Framework могут потребовать изменения кода вашего приложения. Ознакомьтесь со статьей [Совместимость приложений в .NET Framework](application-compatibility.md), прежде чем запускать существующие приложения в .NET Framework 4.5 или более поздних версий. Дополнительные сведения об установке текущей версии см. в разделе [Установка .NET Framework для разработчиков](../install/guide-for-developers.md). Сведения о поддержке платформы .NET Framework см. на странице [Официальная политика поддержки .NET Framework](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) веб-сайта .NET.

## <a name="remarks-for-older-versions"></a>Комментарии для устаревших версий

Версии .NET Framework 2.0, 3.0 и 3.5 построены на базе одной и той же версии среды CLR (CLR 2.0). Эти версии представляют последовательные уровни единой установки. Каждая версия построена на базе предыдущих версий. Невозможно запустить версии 2.0, 3.0 и 3.5 параллельно на одном компьютере. При установке версии 3.5 автоматически создаются уровни версий 2.0 и 3.0, и приложения, созданные для версий 2.0, 3.0 и 3.5, могут выполняться в версии 3.5. Тем не менее .NET Framework 4 завершает этот уровневый подход, и этот выпуск — а также более поздние (.NET Framework 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 и 4.8) — представляет последовательные уровни единой установки. Начиная с .NET Framework 4 разработчики могут использовать внутрипроцессное параллельное размещение для запуска нескольких версий среды CLR в одном процессе. Дополнительные сведения см. в разделе [Сборки и параллельное выполнение](../../standard/assembly/side-by-side-execution.md).

Кроме того, если в приложении выбрана целевая платформа версии 2.0, 3.0 или 3.5, пользователям может потребоваться включить .NET Framework 3.5 на компьютере с Windows 8, Windows 8.1 или Windows 10, прежде чем они смогут запустить это приложение. Дополнительные сведения см. в разделе [Установка .NET Framework 3.5 в Windows 10, Windows 8.1 и Windows 8](../install/dotnet-35-windows-10.md).

## <a name="next-steps"></a>Дальнейшие действия

- Если у вас отсутствует опыт работы с .NET Framework, [ознакомьтесь](../get-started/overview.md) с общими сведениями об этой платформе, основными понятиями и ключевыми функциями.

- Сведения о новых функциях и улучшениях в .NET Framework 4.5 и ее доработанных выпусках см. в разделе [Новые возможности в .NET Framework](../whats-new/index.md).

- Сведения о миграции приложения на более новую версию платформы .NET Framework см. в [руководстве по миграции](index.md).

- Сведения об определении версий или обновлений, установленных на компьютере, см. в разделах [Практическое руководство. Определение установленных версий .NET Framework](how-to-determine-which-versions-are-installed.md) и [Практическое руководство. Определение установленных обновлений .NET Framework](how-to-determine-which-net-framework-updates-are-installed.md).

## <a name="see-also"></a>См. также раздел

- [Совместимость версий в .NET Framework](version-compatibility.md)
| [.NET Framework Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) (Политика поддержки .NET Framework)
- [Устранение неполадок с заблокированными установками и удалениями .NET Framework](../install/troubleshoot-blocked-installations-and-uninstallations.md)
