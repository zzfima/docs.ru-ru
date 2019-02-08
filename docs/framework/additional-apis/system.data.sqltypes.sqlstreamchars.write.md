---
title: SqlStreamChars.Write(Char[], Int32, Int32) Method (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: e2b0d2c4e68ffa0c0b9e745a15dbb8c79659008c
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826035"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="a18aa-102">Метод SqlStreamChars.Write (Char [], Int32, Int32)</span><span class="sxs-lookup"><span data-stu-id="a18aa-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="a18aa-103">При переопределении в производном классе, записывает последовательность символов в текущий поток и перемещает текущую позицию внутри потока на число записанных символов.</span><span class="sxs-lookup"><span data-stu-id="a18aa-103">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="a18aa-104">Дружественные сборки, содержащей этот метод связан с SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="a18aa-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="a18aa-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a18aa-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="a18aa-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="a18aa-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="a18aa-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="a18aa-107">Parameters</span></span>

`buffer`  
<span data-ttu-id="a18aa-108">Записываемый массив char.</span><span class="sxs-lookup"><span data-stu-id="a18aa-108">A char array to write.</span></span>

`offset`  
<span data-ttu-id="a18aa-109">Смещение относительно начала координат.</span><span class="sxs-lookup"><span data-stu-id="a18aa-109">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="a18aa-110">Число символов для записи в текущий поток.</span><span class="sxs-lookup"><span data-stu-id="a18aa-110">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="a18aa-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="a18aa-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="a18aa-112">`SqlStreamChars.Write` Метод является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="a18aa-112">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a18aa-113">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="a18aa-113">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a18aa-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a18aa-114">Requirements</span></span>

<span data-ttu-id="a18aa-115">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="a18aa-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="a18aa-116">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="a18aa-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="a18aa-117">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="a18aa-117">**.NET Framework versions:** Available since 2.0.</span></span>