---
title: "Методы System.Convert"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 88193d7d8ca1544ad8db0947ff670f30ebddaa7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="systemconvert-methods"></a><span data-ttu-id="eef76-102">Методы System.Convert</span><span class="sxs-lookup"><span data-stu-id="eef76-102">System.Convert Methods</span></span>
<span data-ttu-id="eef76-103">Ниже перечислены методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], не поддерживаемые технологией <xref:System.Convert>.</span><span class="sxs-lookup"><span data-stu-id="eef76-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not support the following <xref:System.Convert> methods.</span></span>  
  
-   <span data-ttu-id="eef76-104">Версии с параметром <xref:System.IFormatProvider>.</span><span class="sxs-lookup"><span data-stu-id="eef76-104">Versions with an <xref:System.IFormatProvider> parameter.</span></span>  
  
-   <span data-ttu-id="eef76-105">Методы, включающие символьные и байтовые массивы.</span><span class="sxs-lookup"><span data-stu-id="eef76-105">Methods that involve char arrays or byte arrays:</span></span>  
  
    -   <xref:System.Convert.FromBase64CharArray%2A>  
  
    -   <xref:System.Convert.ToBase64CharArray%2A>  
  
    -   <xref:System.Convert.FromBase64String%2A>  
  
    -   <xref:System.Convert.ToBase64String%2A>  
  
-   <span data-ttu-id="eef76-106">Следующие методы:</span><span class="sxs-lookup"><span data-stu-id="eef76-106">The following methods:</span></span>  
  
    -   <span data-ttu-id="eef76-107">`public static <Type2> To<Type2>(<Type1> value);`, где</span><span class="sxs-lookup"><span data-stu-id="eef76-107">`public static <Type2> To<Type2>(<Type1> value);` where</span></span>  
  
         <span data-ttu-id="eef76-108">`Type1` и `Type2` имеют тип `sbyte`, `uint`, `ulong` или `ushort`.</span><span class="sxs-lookup"><span data-stu-id="eef76-108">`Type1` and `Type2` are each one of `sbyte`, `uint`, `ulong`, or `ushort`.</span></span>  
  
    -   <span data-ttu-id="eef76-109">C#:</span><span class="sxs-lookup"><span data-stu-id="eef76-109">C#:</span></span>  
  
         `int To<int type>(string value, int fromBase),`  
  
         `ToString(... value, int toBase)`  
  
    -   <span data-ttu-id="eef76-110">Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="eef76-110">Visual Basic:</span></span>  
  
         `Function To(Of [Numeric])(value as String, fromBase As Integer)`  
  
         `As [Numeric], ToString( value As …, toBase As Integer)`  
  
    -   <xref:System.Convert.IsDBNull%2A>  
  
    -   <xref:System.Convert.GetTypeCode%2A>  
  
    -   <xref:System.Convert.ChangeType%2A>  
  
## <a name="see-also"></a><span data-ttu-id="eef76-111">См. также</span><span class="sxs-lookup"><span data-stu-id="eef76-111">See Also</span></span>  
 [<span data-ttu-id="eef76-112">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="eef76-112">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
