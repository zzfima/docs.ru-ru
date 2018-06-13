---
title: Допускающие значения null структурированные типы (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: 6b949cebfa1b16f8e6fb5a133c61c5668d90b3bf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762391"
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="9968f-102">Допускающие значения null структурированные типы (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9968f-102">Nullable Structured Types (Entity SQL)</span></span>
<span data-ttu-id="9968f-103">Экземпляр `null` структурированного типа - несуществующий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="9968f-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="9968f-104">Это отличается от существующего экземпляра, все свойства которого имеют значения `null`.</span><span class="sxs-lookup"><span data-stu-id="9968f-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="9968f-105">В этом разделе описаны структурированные типы, допускающие значение NULL, с указанием, какие типы допускают значение NULL и какие последовательности программного кода формируют экземпляры `null` структурированных типов, допускающих значение NULL.</span><span class="sxs-lookup"><span data-stu-id="9968f-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="9968f-106">Разновидности структурированных типов, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="9968f-106">Kinds of Nullable Structured Types</span></span>  
 <span data-ttu-id="9968f-107">Существует три разновидности структурированных типов, допускающих значение NULL:</span><span class="sxs-lookup"><span data-stu-id="9968f-107">There are three kinds of nullable structure types:</span></span>  
  
-   <span data-ttu-id="9968f-108">Типы строк.</span><span class="sxs-lookup"><span data-stu-id="9968f-108">Row types.</span></span>  
  
-   <span data-ttu-id="9968f-109">Сложные типы.</span><span class="sxs-lookup"><span data-stu-id="9968f-109">Complex types.</span></span>  
  
-   <span data-ttu-id="9968f-110">Типы сущностей.</span><span class="sxs-lookup"><span data-stu-id="9968f-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="9968f-111">Шаблоны кода, которые формируют экземпляры NULL структурированных типов</span><span class="sxs-lookup"><span data-stu-id="9968f-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  
 <span data-ttu-id="9968f-112">В следующем сценарии формируются экземпляры `null`:</span><span class="sxs-lookup"><span data-stu-id="9968f-112">The following scenarios produce `null` instances:</span></span>  
  
-   <span data-ttu-id="9968f-113">Формирование `null` как структурированного типа:</span><span class="sxs-lookup"><span data-stu-id="9968f-113">Shaping `null` as a structured type:</span></span>  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   <span data-ttu-id="9968f-114">Приведение базового типа к производному типу:</span><span class="sxs-lookup"><span data-stu-id="9968f-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   <span data-ttu-id="9968f-115">Внешнее соединение по условию FALSE:</span><span class="sxs-lookup"><span data-stu-id="9968f-115">Outer join on false condition:</span></span>  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="9968f-116">--или</span><span class="sxs-lookup"><span data-stu-id="9968f-116">--or</span></span>  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="9968f-117">--или</span><span class="sxs-lookup"><span data-stu-id="9968f-117">--or</span></span>  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   <span data-ttu-id="9968f-118">Разыменование ссылки на `null`:</span><span class="sxs-lookup"><span data-stu-id="9968f-118">Dereferencing a `null` reference:</span></span>  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   <span data-ttu-id="9968f-119">Получение значения ANYELEMENT из пустой коллекции:</span><span class="sxs-lookup"><span data-stu-id="9968f-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   <span data-ttu-id="9968f-120">Проверка наличия экземпляров `null` структурированных типов:</span><span class="sxs-lookup"><span data-stu-id="9968f-120">Checking for `null` instances of structured types:</span></span>  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9968f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9968f-121">See Also</span></span>  
 [<span data-ttu-id="9968f-122">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9968f-122">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
