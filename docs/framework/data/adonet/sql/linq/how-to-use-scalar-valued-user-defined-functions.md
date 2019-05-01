---
title: Практическое руководство. Как применять определяемые пользователем скалярные функции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: ffb24468c81cb4ec9f41645f8888c2c4ba021609
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033583"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a><span data-ttu-id="9a03d-102">Практическое руководство. Как применять определяемые пользователем скалярные функции</span><span class="sxs-lookup"><span data-stu-id="9a03d-102">How to: Use Scalar-Valued User-Defined Functions</span></span>
<span data-ttu-id="9a03d-103">Для сопоставления клиентского метода, определенного в классе, с пользовательской функцией используется атрибут <xref:System.Data.Linq.Mapping.FunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9a03d-103">You can map a client method defined on a class to a user-defined function by using the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute.</span></span> <span data-ttu-id="9a03d-104">Обратите внимание, что тело метода создает выражение, перехватывающее назначение вызова метода, и передает это выражение в <xref:System.Data.Linq.DataContext> для преобразования и выполнения.</span><span class="sxs-lookup"><span data-stu-id="9a03d-104">Note that the body of the method constructs an expression that captures the intent of the method call, and passes that expression to the <xref:System.Data.Linq.DataContext> for translation and execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a03d-105">Прямое выполнение возможно только при вызове функции вне запроса.</span><span class="sxs-lookup"><span data-stu-id="9a03d-105">Direct execution occurs only if the function is called outside a query.</span></span> <span data-ttu-id="9a03d-106">Дополнительные сведения см. в разделе [Как Вызывать встроенные определяемые пользователем функции](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md).</span><span class="sxs-lookup"><span data-stu-id="9a03d-106">For more information, see [How to: Call User-Defined Functions Inline](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a03d-107">Пример</span><span class="sxs-lookup"><span data-stu-id="9a03d-107">Example</span></span>  
 <span data-ttu-id="9a03d-108">В следующем коде SQL представлена скалярная пользовательская функция `ReverseCustName()`.</span><span class="sxs-lookup"><span data-stu-id="9a03d-108">The following SQL code presents a scalar-valued user-defined function `ReverseCustName()`.</span></span>  
  
```  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 <span data-ttu-id="9a03d-109">Для этого кода следует отобразить клиентский метод, подобный следующему.</span><span class="sxs-lookup"><span data-stu-id="9a03d-109">You would map a client method such as the following for this code:</span></span>  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9a03d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="9a03d-110">See also</span></span>

- [<span data-ttu-id="9a03d-111">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="9a03d-111">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
