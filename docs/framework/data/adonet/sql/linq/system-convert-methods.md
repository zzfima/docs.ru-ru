---
title: Методы System.Convert
ms.date: 03/30/2017
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
ms.openlocfilehash: d0aa0b11223e23b874471962d727d8e16e152ceb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781056"
---
# <a name="systemconvert-methods"></a><span data-ttu-id="4af39-102">Методы System.Convert</span><span class="sxs-lookup"><span data-stu-id="4af39-102">System.Convert Methods</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="4af39-103">не поддерживает следующие методы <xref:System.Convert>.</span><span class="sxs-lookup"><span data-stu-id="4af39-103">does not support the following <xref:System.Convert> methods.</span></span>

- <span data-ttu-id="4af39-104">Версии с параметром <xref:System.IFormatProvider>.</span><span class="sxs-lookup"><span data-stu-id="4af39-104">Versions with an <xref:System.IFormatProvider> parameter.</span></span>

- <span data-ttu-id="4af39-105">Методы, включающие символьные и байтовые массивы.</span><span class="sxs-lookup"><span data-stu-id="4af39-105">Methods that involve char arrays or byte arrays:</span></span>

  - <xref:System.Convert.FromBase64CharArray%2A>

  - <xref:System.Convert.ToBase64CharArray%2A>

  - <xref:System.Convert.FromBase64String%2A>

  - <xref:System.Convert.ToBase64String%2A>

- <span data-ttu-id="4af39-106">Следующие методы:</span><span class="sxs-lookup"><span data-stu-id="4af39-106">The following methods:</span></span>

  - <span data-ttu-id="4af39-107">`public static <Type2> To<Type2>(<Type1> value);`, где</span><span class="sxs-lookup"><span data-stu-id="4af39-107">`public static <Type2> To<Type2>(<Type1> value);` where</span></span>

    <span data-ttu-id="4af39-108">`Type1` и `Type2` имеют тип `sbyte`, `uint`, `ulong` или `ushort`.</span><span class="sxs-lookup"><span data-stu-id="4af39-108">`Type1` and `Type2` are each one of `sbyte`, `uint`, `ulong`, or `ushort`.</span></span>

  - <span data-ttu-id="4af39-109">C#:</span><span class="sxs-lookup"><span data-stu-id="4af39-109">C#:</span></span>

    `int To<int type>(string value, int fromBase),`

    `ToString(... value, int toBase)`

  - <span data-ttu-id="4af39-110">Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="4af39-110">Visual Basic:</span></span>

    `Function To(Of [Numeric])(value as String, fromBase As Integer)`

    `As [Numeric], ToString( value As …, toBase As Integer)`

  - <xref:System.Convert.IsDBNull%2A>

  - <xref:System.Convert.GetTypeCode%2A>

  - <xref:System.Convert.ChangeType%2A>

## <a name="see-also"></a><span data-ttu-id="4af39-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4af39-111">See also</span></span>

- [<span data-ttu-id="4af39-112">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="4af39-112">Data Types and Functions</span></span>](data-types-and-functions.md)
