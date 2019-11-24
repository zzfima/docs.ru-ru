---
title: Общие сведения о безопасности модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: 70d24c3dcc531abcec6d4dce75b5f0b31757e0c0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448772"
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="bd6f3-102">Общие сведения о безопасности модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="bd6f3-102">UI Automation Security Overview</span></span>

> [!NOTE]
> <span data-ttu-id="bd6f3-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="bd6f3-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="bd6f3-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="bd6f3-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>

<span data-ttu-id="bd6f3-105">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-105">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista.</span></span>

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a><span data-ttu-id="bd6f3-106">контроль учетных записей</span><span class="sxs-lookup"><span data-stu-id="bd6f3-106">User Account Control</span></span>

<span data-ttu-id="bd6f3-107">Security is a major focus of Windows Vista and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-107">Security is a major focus of Windows Vista and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>

<span data-ttu-id="bd6f3-108">In Windows Vista, most applications are supplied with either a standard or an administrative token.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-108">In Windows Vista, most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="bd6f3-109">Если приложение не идентифицировано как административное приложение, оно запускается в качестве стандартного приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-109">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="bd6f3-110">Before an application identified as administrative can be launched, Windows Vista prompts the user for consent to run the application as elevated.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-110">Before an application identified as administrative can be launched, Windows Vista prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="bd6f3-111">Запрос на продолжение отображается по умолчанию, даже если пользователь является членом локальной группы администраторов, так как администраторы выполняют запуск как обычные пользователи, пока приложение или системный компонент, которому требуются административные учетные данные, не запросит разрешение на запуск.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-111">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="bd6f3-112">Задачи, требующие повышенных привилегий</span><span class="sxs-lookup"><span data-stu-id="bd6f3-112">Tasks Requiring Higher Privileges</span></span>

<span data-ttu-id="bd6f3-113">When a user attempts to perform a task that requires administrative privileges, Windows Vista presents a dialog box asking the user for consent to continue.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-113">When a user attempts to perform a task that requires administrative privileges, Windows Vista presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="bd6f3-114">Это диалоговое окно защищено от межпроцессного взаимодействия, чтобы вредоносные программы не могли имитировать ввод данных пользователем.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-114">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="bd6f3-115">Аналогичным образом экран входа в систему обычно недоступен для других процессов.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-115">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>

<span data-ttu-id="bd6f3-116">Клиенты автоматизации пользовательского интерфейса должны взаимодействовать с другими процессами, а некоторые из них могут запускаться с повышенным уровнем привилегий.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-116">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="bd6f3-117">Клиентам также может требоваться доступ к диалоговым окнам системы, которые обычно невидимы для других процессов.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-117">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="bd6f3-118">Таким образом, клиенты [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] должны быть доверенными для системы и должны запускаться со специальными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-118">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>

<span data-ttu-id="bd6f3-119">Чтобы быть доверенными для взаимодействия с приложениями, работающими на более высоком уровне привилегий, приложения должны быть подписаны.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-119">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a><span data-ttu-id="bd6f3-120">Файлы манифеста</span><span class="sxs-lookup"><span data-stu-id="bd6f3-120">Manifest Files</span></span>

<span data-ttu-id="bd6f3-121">To gain access to the protected system UI, applications must be built with a manifest file that includes the `uiAccess` attribute in the `requestedExecutionLevel` tag, as follows:</span><span class="sxs-lookup"><span data-stu-id="bd6f3-121">To gain access to the protected system UI, applications must be built with a manifest file that includes the `uiAccess` attribute in the `requestedExecutionLevel` tag, as follows:</span></span>

```xml
<trustInfo xmlns="urn:schemas-microsoft-com:asm.v3">
  <security>
    <requestedPrivileges>
      <requestedExecutionLevel
        level="highestAvailable"
        uiAccess="true" />
    </requestedPrivileges>
  </security>
</trustInfo>
```

<span data-ttu-id="bd6f3-122">Значение атрибута `level` в этом коде приводится только для примера.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-122">The value of the `level` attribute in this code is an example only.</span></span>

<span data-ttu-id="bd6f3-123">`uiAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected UI.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-123">`uiAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected UI.</span></span>
