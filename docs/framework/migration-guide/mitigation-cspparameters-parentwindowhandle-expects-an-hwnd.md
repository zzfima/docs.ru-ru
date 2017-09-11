---
title: "Устранение рисков: CspParameters.ParentWindowHandle ожидает HWND"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- CspParameters.ParentWindowHandle
- CspParameters.ParentWindowHandle retargeting change
ms.assetid: 33264333-71d6-4d43-8827-9c98878cfea7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1b65aaf7149ca29b2af3efdf44ee9489a04c73a2
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-cspparametersparentwindowhandle-expects-an-hwnd"></a><span data-ttu-id="c564e-102">Устранение рисков: CspParameters.ParentWindowHandle ожидает HWND</span><span class="sxs-lookup"><span data-stu-id="c564e-102">Mitigation: CspParameters.ParentWindowHandle Expects an HWND</span></span>

<span data-ttu-id="c564e-103">Свойство <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>, которое появилось в .NET Framework 2.0, позволяет приложению зарегистрировать значение дескриптора родительского окна таким образом, что любой пользовательский интерфейс, необходимый для доступа к ключу (например, запрос ПИН-кода или окно согласия), будет открываться в режиме модального дочернего окна для указанного окна.</span><span class="sxs-lookup"><span data-stu-id="c564e-103">The <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property, introduced in the .NET Framework 2.0, allows an application to register a parent window handle value such that any UI required to access the key (such as a PIN prompt or a consent dialog) opens as a modal child to the specified window.</span></span> <span data-ttu-id="c564e-104">В приложениях, ориентированных на .NET Framework версии 4.7, этому свойству можно назначить дескриптор окна (HWND).</span><span class="sxs-lookup"><span data-stu-id="c564e-104">Starting with applications that target the .NET Framework 4.7, a window handle (HWND) can be assigned to this property.</span></span>

<span data-ttu-id="c564e-105">В версиях .NET Framework до 4.6.2 для значения, присваиваемого свойству <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>, ожидался тип <xref:System.IntPtr>, представляющий расположение в памяти, где находилось значение HWND.</span><span class="sxs-lookup"><span data-stu-id="c564e-105">In versions of the .NET Framework through the .NET Framework 4.6.2, the value assigned to the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property was expected to be an <xref:System.IntPtr> that represents the location in memory where the HWND value resided.</span></span> <span data-ttu-id="c564e-106">В Windows 7 и более ранних версиях операционной системы Windows задание свойству значения `form.Handle` не на что не влияло, но в Windows 8 и более поздних версиях оно приводит к <xref:System.Security.Cryptography> с сообщением "Неверный параметр".</span><span class="sxs-lookup"><span data-stu-id="c564e-106">On Windows 7 and earlier versions of the Windows operating system, setting the property to `form.Handle` had no effect, but on Windows 8 and later versions, it results in a <xref:System.Security.Cryptography> with the message, "The parameter is incorrect."</span></span>

<span data-ttu-id="c564e-107">Начиная с приложений, предназначенных для .NET Framework 4.7, приложение Windows Forms может установить значение свойства <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="c564e-107">Starting with apps that target the .NET Framework 4.7, a Windows Forms application can set the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property with code like the following:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="impact"></a><span data-ttu-id="c564e-108">Последствия</span><span class="sxs-lookup"><span data-stu-id="c564e-108">Impact</span></span>

<span data-ttu-id="c564e-109">В приложениях, ориентированных на .NET Framework не старше версии 4.7, в которых нужно зарегистрировать связь с родительским окном, рекомендуется использовать упрощенную форму:</span><span class="sxs-lookup"><span data-stu-id="c564e-109">Applications targeting the .NET Framework 4.7 or later that wish to register a parent window relationship are encouraged to use the simplified form:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="mitigation"></a><span data-ttu-id="c564e-110">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="c564e-110">Mitigation</span></span>

<span data-ttu-id="c564e-111">Разработчики, которые определили, что правильным значением был адрес области памяти, в которой содержалось значение `form.Handle`, могут отказаться от этого изменения в поведении, установив параметру `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` переключателя <xref:System.AppContext> значение `true`:</span><span class="sxs-lookup"><span data-stu-id="c564e-111">Developers who had identified that the correct value was the address of the memory location that held the `form.Handle` value can opt out of this change in behavior by setting the <xref:System.AppContext> switch `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` to `true`:</span></span>

- <span data-ttu-id="c564e-112">путем программной установки переключателей совместимости в экземпляре <xref:System.AppContext>;</span><span class="sxs-lookup"><span data-stu-id="c564e-112">By programmatically setting compatibility switches on the <xref:System.AppContext> instance.</span></span>

- <span data-ttu-id="c564e-113">путем добавления следующей строки в раздел `<runtime>` файла app.config:</span><span class="sxs-lookup"><span data-stu-id="c564e-113">By adding the following line to the `<runtime>` section of the app.config file:</span></span>
   
   ```xml
   <runtime>
     <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
   </runtime>
   ```

<span data-ttu-id="c564e-114">Пользователи, которые хотят изменить поведение приложений, выполняемых на платформе .NET Framework 4.7, но ориентированных на более ранние версии платформы .NET Framework, могут задать переключателю <xref:System.AppContext> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="c564e-114">Conversely, users who wish to opt in to the new behavior for applications that run under the .NET Framework 4.7 but target an earlier version of the .NET Framework versions can set the <xref:System.AppContext> switch to `false`.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="c564e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c564e-115">See also</span></span>

[<span data-ttu-id="c564e-116">Изменения целевой платформы в .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="c564e-116">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

