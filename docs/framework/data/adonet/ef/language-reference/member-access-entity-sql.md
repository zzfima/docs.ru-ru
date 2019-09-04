---
title: . (Доступ к членам) (язык Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 1db6be632da90eaa7a761bb213e395182ae42347
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250297"
---
# <a name="-member-access-entity-sql"></a><span data-ttu-id="828a7-103">.</span><span class="sxs-lookup"><span data-stu-id="828a7-103">.</span></span> <span data-ttu-id="828a7-104">(Доступ к членам) (язык Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="828a7-104">(Member Access) (Entity SQL)</span></span>
<span data-ttu-id="828a7-105">Оператор "точка" (.) является [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="828a7-105">The dot operator (.) is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] member access operator.</span></span> <span data-ttu-id="828a7-106">Оператор доступа к элементу можно использовать, чтобы выдавать значение свойства или поля экземпляра структурного типа концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="828a7-106">You use the member access operator to yield the value of a property or field of an instance of structural conceptual model type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="828a7-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="828a7-107">Syntax</span></span>  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a><span data-ttu-id="828a7-108">Аргументы</span><span class="sxs-lookup"><span data-stu-id="828a7-108">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="828a7-109">Экземпляр структурного типа концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="828a7-109">An instance of a structural conceptual model type.</span></span>  
  
 `identifier`  
 <span data-ttu-id="828a7-110">Свойство или поле, принадлежащее экземпляру объекта.</span><span class="sxs-lookup"><span data-stu-id="828a7-110">A property or field that belongs to an object instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="828a7-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="828a7-111">Remarks</span></span>  
 <span data-ttu-id="828a7-112">Оператор «точка» (.) можно использовать для извлечения полей из записи подобно извлечению свойств сложного типа или типа сущности.</span><span class="sxs-lookup"><span data-stu-id="828a7-112">The dot (.) operator may be used to extract fields from a record, similar to extracting properties of a complex or entity type.</span></span> <span data-ttu-id="828a7-113">Например, если «n» типа Name является элементом типа Name, а «p» является элементом типа Person, то «p.n» будет допустимым выражением доступа к элементу, которое выдаст значение типа Name.</span><span class="sxs-lookup"><span data-stu-id="828a7-113">For example, if n of type Name is a member of type Person, and p is an instance of type Person, then p.n is a legal member access expression that yields a value of type Name.</span></span>  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a><span data-ttu-id="828a7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="828a7-114">See also</span></span>

- [<span data-ttu-id="828a7-115">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="828a7-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
