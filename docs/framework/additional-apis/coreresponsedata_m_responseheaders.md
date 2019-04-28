---
title: Поле CoreResponseData.m_ResponseHeaders
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
ms.openlocfilehash: ea93b70ae8e1a710b4208050d7ec823a28b218b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705978"
---
# <a name="coreresponsedatamresponseheaders-field"></a><span data-ttu-id="c886c-102">CoreResponseData.m\_ResponseHeaders поля</span><span class="sxs-lookup"><span data-stu-id="c886c-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="c886c-103">`CoreResponseData.m_ResponseHeaders` является <xref:System.Net.WebHeaderCollection> заголовков, связанные с ответом сервера.</span><span class="sxs-lookup"><span data-stu-id="c886c-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="c886c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c886c-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="c886c-105">Этот API не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="c886c-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="c886c-106">Вместо этого следует использовать <xref:System.Diagnostics.DiagnosticSource> для подключения сетевого кода.</span><span class="sxs-lookup"><span data-stu-id="c886c-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="c886c-107">См. в разделе [руководство пользователя DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="c886c-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="c886c-108">Майкрософт не поддерживает использование этого класса в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="c886c-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c886c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c886c-109">Requirements</span></span>

<span data-ttu-id="c886c-110">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="c886c-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="c886c-111">**Сборка:** Системы (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="c886c-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="c886c-112">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="c886c-112">**.NET Framework versions:** Available since 2.0.</span></span>
