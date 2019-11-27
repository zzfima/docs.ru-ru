---
title: Метод MemoryStream. Интерналжеторигинандленгс (System.IO)
author: mairaw
ms.author: mairaw
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: d2bfa087fe2fb247f963cfa687c27056363d5696
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74284045"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a><span data-ttu-id="e5fb0-102">Метод MemoryStream. Интерналжеторигинандленгс</span><span class="sxs-lookup"><span data-stu-id="e5fb0-102">MemoryStream.InternalGetOriginAndLength method</span></span>

<span data-ttu-id="e5fb0-103">Возвращает внутренние значения источника и длину потока памяти.</span><span class="sxs-lookup"><span data-stu-id="e5fb0-103">Gets the internal values of origin and length of the memory stream.</span></span>

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a><span data-ttu-id="e5fb0-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5fb0-104">Parameters</span></span>

- <span data-ttu-id="e5fb0-105">`origin` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="e5fb0-105">`origin` <xref:System.Int32></span></span>\
  <span data-ttu-id="e5fb0-106">При возврате из этого метода смещение массива байтов, указанного при создании нового объекта <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="e5fb0-106">When this method returns, the offset of the byte array specified when creating a new <xref:System.IO.MemoryStream> object.</span></span> <span data-ttu-id="e5fb0-107">Содержит 0, если массив байтов был создан <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="e5fb0-107">Contains 0 if the byte array was created by <xref:System.IO.MemoryStream>.</span></span>

- <span data-ttu-id="e5fb0-108">`length` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="e5fb0-108">`length` <xref:System.Int32></span></span>\
  <span data-ttu-id="e5fb0-109">При возврате из этого метода число байтов в потоке памяти.</span><span class="sxs-lookup"><span data-stu-id="e5fb0-109">When this method returns, the number of bytes within the memory stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5fb0-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="e5fb0-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e5fb0-111">Метод `MemoryStream.InternalGetOriginAndLength` является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="e5fb0-111">The `MemoryStream.InternalGetOriginAndLength` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e5fb0-112">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="e5fb0-112">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e5fb0-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e5fb0-113">Requirements</span></span>

<span data-ttu-id="e5fb0-114">**Пространство имен:** <xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="e5fb0-114">**Namespace:** <xref:System.IO></span></span>

<span data-ttu-id="e5fb0-115">**Сборка:** mscorlib. dll (в mscorlib. dll)</span><span class="sxs-lookup"><span data-stu-id="e5fb0-115">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="e5fb0-116">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="e5fb0-116">**.NET Framework versions:** Available since 2.0.</span></span>
