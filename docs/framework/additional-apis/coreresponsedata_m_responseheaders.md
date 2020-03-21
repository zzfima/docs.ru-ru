---
title: CoreResponseData.m_ResponseHeaders Поле
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 723df6dc2de978695608d106e3a01bde286fc4fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156107"
---
# <a name="coreresponsedatam_responseheaders-field"></a><span data-ttu-id="d63f6-102">CoreResponseData.m\_ResponseHeaders Field</span><span class="sxs-lookup"><span data-stu-id="d63f6-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="d63f6-103">`CoreResponseData.m_ResponseHeaders`— <xref:System.Net.WebHeaderCollection> это заголовки, связанные с ответом сервера.</span><span class="sxs-lookup"><span data-stu-id="d63f6-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="d63f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d63f6-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="d63f6-105">Этот API не предназначен для использования непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="d63f6-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="d63f6-106">Вместо этого следует <xref:System.Diagnostics.DiagnosticSource> использовать сетевой код.</span><span class="sxs-lookup"><span data-stu-id="d63f6-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="d63f6-107">Смотрите [руководство DiagnosticSource пользователя](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="d63f6-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="d63f6-108">Корпорация Майкрософт ни при каких обстоятельствах не поддерживает использование этого класса в производственном приложении.</span><span class="sxs-lookup"><span data-stu-id="d63f6-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d63f6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d63f6-109">Requirements</span></span>

<span data-ttu-id="d63f6-110">**Пространство имен:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="d63f6-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="d63f6-111">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="d63f6-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="d63f6-112">**Рамочные версии .NET:** Доступно с 2.0.</span><span class="sxs-lookup"><span data-stu-id="d63f6-112">**.NET Framework versions:** Available since 2.0.</span></span>
