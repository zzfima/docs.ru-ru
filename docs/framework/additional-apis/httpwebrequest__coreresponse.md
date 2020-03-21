---
title: HttpWebRequest._CoreResponse поле
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: b275f3eece96ac8a9ae3fb0ebd030c8d79e21fc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155925"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="7f41a-102">HttpWebRequest. \_Поле CoreResponse</span><span class="sxs-lookup"><span data-stu-id="7f41a-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="7f41a-103">`HttpWebRequest._CoreResponse`— объект (либо [CoreResponseData,](coreresponsedata.md) либо <xref:System.Exception>), содержащий результат анализа ответов HTTP.</span><span class="sxs-lookup"><span data-stu-id="7f41a-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="7f41a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f41a-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="7f41a-105">Этот API не предназначен для использования непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="7f41a-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="7f41a-106">Вместо этого следует <xref:System.Diagnostics.DiagnosticSource> использовать сетевой код.</span><span class="sxs-lookup"><span data-stu-id="7f41a-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="7f41a-107">Смотрите [руководство DiagnosticSource пользователя](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="7f41a-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="7f41a-108">Корпорация Майкрософт ни при каких обстоятельствах не поддерживает использование этого класса в производственном приложении.</span><span class="sxs-lookup"><span data-stu-id="7f41a-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7f41a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7f41a-109">Requirements</span></span>

<span data-ttu-id="7f41a-110">**Пространство имен:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="7f41a-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="7f41a-111">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="7f41a-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="7f41a-112">**Рамочные версии .NET:** Доступно с 2.0.</span><span class="sxs-lookup"><span data-stu-id="7f41a-112">**.NET Framework versions:** Available since 2.0.</span></span>
