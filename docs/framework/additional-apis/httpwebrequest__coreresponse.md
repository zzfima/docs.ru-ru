---
title: "Поле HttpWebRequest._CoreResponse"
ms.date: 01/29/2018
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.author: stwhi
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: e6493747cf6c894357223f011da026770778e26c
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="httpwebrequestcoreresponse-field"></a><span data-ttu-id="c1360-102">HttpWebRequest. \_CoreResponse поля</span><span class="sxs-lookup"><span data-stu-id="c1360-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="c1360-103">`HttpWebRequest._CoreResponse`— Это объект (либо [CoreResponseData](coreresponsedata.md) или <xref:System.Exception>) содержащий результат синтаксическом разборе ответа HTTP.</span><span class="sxs-lookup"><span data-stu-id="c1360-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="c1360-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1360-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="c1360-105">Этот API не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="c1360-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="c1360-106">Вместо этого следует использовать <xref:System.Diagnostics.DiagnosticSource> отключают сетевого кода.</span><span class="sxs-lookup"><span data-stu-id="c1360-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="c1360-107">В разделе [DiagnosticSource в руководстве пользователя](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="c1360-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="c1360-108">В реальном приложении ни при каких обстоятельствах корпорация Майкрософт не поддерживает использование этого класса.</span><span class="sxs-lookup"><span data-stu-id="c1360-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c1360-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c1360-109">Requirements</span></span>

<span data-ttu-id="c1360-110">**Пространство имен:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="c1360-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="c1360-111">**Сборка:** системы (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="c1360-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="c1360-112">**Версии платформы .NET framework:** доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="c1360-112">**.NET Framework versions:** Available since 2.0.</span></span>
