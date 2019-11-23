---
title: Практическое руководство. Использование пользовательских скалярных функций
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: dfe82fd50eb3eedeaff9082a4288901f72197795
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003239"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a><span data-ttu-id="5005d-102">Практическое руководство. Использование пользовательских скалярных функций</span><span class="sxs-lookup"><span data-stu-id="5005d-102">How to: Use Scalar-Valued User-Defined Functions</span></span>
<span data-ttu-id="5005d-103">Для сопоставления клиентского метода, определенного в классе, с пользовательской функцией используется атрибут <xref:System.Data.Linq.Mapping.FunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5005d-103">You can map a client method defined on a class to a user-defined function by using the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute.</span></span> <span data-ttu-id="5005d-104">Обратите внимание, что тело метода создает выражение, перехватывающее назначение вызова метода, и передает это выражение в <xref:System.Data.Linq.DataContext> для преобразования и выполнения.</span><span class="sxs-lookup"><span data-stu-id="5005d-104">Note that the body of the method constructs an expression that captures the intent of the method call, and passes that expression to the <xref:System.Data.Linq.DataContext> for translation and execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5005d-105">Прямое выполнение возможно только при вызове функции вне запроса.</span><span class="sxs-lookup"><span data-stu-id="5005d-105">Direct execution occurs only if the function is called outside a query.</span></span> <span data-ttu-id="5005d-106">Дополнительные сведения см. [в разделе инструкции. Вызов определяемых пользователем функций в встроенном](how-to-call-user-defined-functions-inline.md)виде.</span><span class="sxs-lookup"><span data-stu-id="5005d-106">For more information, see [How to: Call User-Defined Functions Inline](how-to-call-user-defined-functions-inline.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5005d-107">Пример</span><span class="sxs-lookup"><span data-stu-id="5005d-107">Example</span></span>  
 <span data-ttu-id="5005d-108">В следующем коде SQL представлена скалярная пользовательская функция `ReverseCustName()`.</span><span class="sxs-lookup"><span data-stu-id="5005d-108">The following SQL code presents a scalar-valued user-defined function `ReverseCustName()`.</span></span>  
  
```sql  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 <span data-ttu-id="5005d-109">Для этого кода следует отобразить клиентский метод, подобный следующему.</span><span class="sxs-lookup"><span data-stu-id="5005d-109">You would map a client method such as the following for this code:</span></span>  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="5005d-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="5005d-110">See also</span></span>

- [<span data-ttu-id="5005d-111">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="5005d-111">User-Defined Functions</span></span>](user-defined-functions.md)
