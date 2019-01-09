---
title: Свойство SqlChars.Stream (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlChars.Stream
- System.Data.SqlTypes.SqlChars.get_Stream
- System.Data.SqlTypes.SqlChars.set_Stream
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: f8b6f4f3a92f1d78e434263c6a7897641867c412
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152607"
---
# <a name="sqlcharsstream-property"></a><span data-ttu-id="e912b-102">Свойство SqlChars.Stream</span><span class="sxs-lookup"><span data-stu-id="e912b-102">SqlChars.Stream Property</span></span>

<span data-ttu-id="e912b-103">Возвращает или задает поток символов.</span><span class="sxs-lookup"><span data-stu-id="e912b-103">Gets or sets the character stream.</span></span> <span data-ttu-id="e912b-104">Сборка, содержащая это свойство имеет с SQLAccess.dll связью.</span><span class="sxs-lookup"><span data-stu-id="e912b-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="e912b-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e912b-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="e912b-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="e912b-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="e912b-107">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="e912b-107">Property value</span></span>

`System.Data.SqlTypes.SqlStreamChars`\
<span data-ttu-id="e912b-108">Поток символов.</span><span class="sxs-lookup"><span data-stu-id="e912b-108">The character stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="e912b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="e912b-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e912b-110">`SqlChars.Stream` Свойство является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="e912b-110">The `SqlChars.Stream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e912b-111">Майкрософт не поддерживает использование этого свойства в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="e912b-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e912b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e912b-112">Requirements</span></span>

<span data-ttu-id="e912b-113">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="e912b-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="e912b-114">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="e912b-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="e912b-115">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="e912b-115">**.NET Framework versions:** Available since 2.0.</span></span>