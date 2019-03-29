---
title: Свойство SqlChars.Stream (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlChars.Stream
- System.Data.SqlTypes.SqlChars.get_Stream
- System.Data.SqlTypes.SqlChars.set_Stream
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 4858d9f8878e5b56a0811edf92a2faa729775156
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634002"
---
# <a name="sqlcharsstream-property"></a><span data-ttu-id="798a8-102">Свойство SqlChars.Stream</span><span class="sxs-lookup"><span data-stu-id="798a8-102">SqlChars.Stream Property</span></span>

<span data-ttu-id="798a8-103">Возвращает или задает поток символов.</span><span class="sxs-lookup"><span data-stu-id="798a8-103">Gets or sets the character stream.</span></span> <span data-ttu-id="798a8-104">Сборка, содержащая это свойство имеет с SQLAccess.dll связью.</span><span class="sxs-lookup"><span data-stu-id="798a8-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="798a8-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="798a8-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="798a8-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="798a8-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="798a8-107">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="798a8-107">Property value</span></span>

`System.Data.SqlTypes.SqlStreamChars`\
<span data-ttu-id="798a8-108">Поток символов.</span><span class="sxs-lookup"><span data-stu-id="798a8-108">The character stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="798a8-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="798a8-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="798a8-110">`SqlChars.Stream` Свойство является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="798a8-110">The `SqlChars.Stream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="798a8-111">Майкрософт не поддерживает использование этого свойства в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="798a8-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="798a8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="798a8-112">Requirements</span></span>

<span data-ttu-id="798a8-113">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="798a8-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="798a8-114">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="798a8-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="798a8-115">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="798a8-115">**.NET Framework versions:** Available since 2.0.</span></span>