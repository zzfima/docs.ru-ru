---
title: ". (Доступ к членам) (язык Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6c9d5d8f2c90273b316379d3c2803835bab3faef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="-member-access-entity-sql"></a><span data-ttu-id="29a63-103">.</span><span class="sxs-lookup"><span data-stu-id="29a63-103">.</span></span> <span data-ttu-id="29a63-104">(Доступ к членам) (язык Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="29a63-104">(Member Access) (Entity SQL)</span></span>
<span data-ttu-id="29a63-105">Точка (.) является [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="29a63-105">The dot operator (.) is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] member access operator.</span></span> <span data-ttu-id="29a63-106">Оператор доступа к элементу можно использовать, чтобы выдавать значение свойства или поля экземпляра структурного типа концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="29a63-106">You use the member access operator to yield the value of a property or field of an instance of structural conceptual model type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29a63-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29a63-107">Syntax</span></span>  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a><span data-ttu-id="29a63-108">Аргументы</span><span class="sxs-lookup"><span data-stu-id="29a63-108">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="29a63-109">Экземпляр структурного типа концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="29a63-109">An instance of a structural conceptual model type.</span></span>  
  
 `identifier`  
 <span data-ttu-id="29a63-110">Свойство или поле, принадлежащее экземпляру объекта.</span><span class="sxs-lookup"><span data-stu-id="29a63-110">A property or field that belongs to an object instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29a63-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="29a63-111">Remarks</span></span>  
 <span data-ttu-id="29a63-112">Оператор «точка» (.) можно использовать для извлечения полей из записи подобно извлечению свойств сложного типа или типа сущности.</span><span class="sxs-lookup"><span data-stu-id="29a63-112">The dot (.) operator may be used to extract fields from a record, similar to extracting properties of a complex or entity type.</span></span> <span data-ttu-id="29a63-113">Например, если «n» типа Name является элементом типа Name, а «p» является элементом типа Person, то «p.n» будет допустимым выражением доступа к элементу, которое выдаст значение типа Name.</span><span class="sxs-lookup"><span data-stu-id="29a63-113">For example, if n of type Name is a member of type Person, and p is an instance of type Person, then p.n is a legal member access expression that yields a value of type Name.</span></span>  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a><span data-ttu-id="29a63-114">См. также</span><span class="sxs-lookup"><span data-stu-id="29a63-114">See Also</span></span>  
 [<span data-ttu-id="29a63-115">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="29a63-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
