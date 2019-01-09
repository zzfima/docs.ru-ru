---
title: Поле s_isDebuggerCheckDisabledForTestPurposes
ms.date: 03/30/2017
ms.technology:
- dotnet-wpf
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: f490ccb4675a434e3f3336723e321f256b10093d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149180"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="c018f-102">Поле s_isDebuggerCheckDisabledForTestPurposes</span><span class="sxs-lookup"><span data-stu-id="c018f-102">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="c018f-103">Это частное поле в `System.Windows.Diagnostics.VisualDiagnostics` класс используется средой Visual Studio, чтобы определить, будет ли выполняться внутренняя проверка для активного отладчика.</span><span class="sxs-lookup"><span data-stu-id="c018f-103">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="c018f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c018f-104">Syntax</span></span>
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  <span data-ttu-id="c018f-105">API в `System.Windows.Diagnostics.VisualDiagnostics` класса доступны только в случае, когда приложение выполняется в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="c018f-105">API's in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="c018f-106">Задайте `s_isDebuggerCheckDisabledForTestPurposes` для `true` для доступа к API вне отладчика.</span><span class="sxs-lookup"><span data-stu-id="c018f-106">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>  
>   
>  <span data-ttu-id="c018f-107">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="c018f-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>  

## <a name="requirements"></a><span data-ttu-id="c018f-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c018f-108">Requirements</span></span>

<span data-ttu-id="c018f-109">**Пространство имен:** <xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="c018f-109">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="c018f-110">**Сборка:** PresentationCore (в PresentationCore.dll)</span><span class="sxs-lookup"><span data-stu-id="c018f-110">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="c018f-111">**Версии платформы .NET framework:** Доступно с версии 4.6.</span><span class="sxs-lookup"><span data-stu-id="c018f-111">**.NET Framework versions:** Available since 4.6.</span></span>