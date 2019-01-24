---
title: Типы данных параметров типа не могут быть определены из этих аргументов
ms.date: 07/20/2015
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
ms.openlocfilehash: 68ed7541d76c1678f9f308ed2cda8afec1231a73
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608723"
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a><span data-ttu-id="5e91e-102">Типы данных параметров типа не могут быть определены из этих аргументов</span><span class="sxs-lookup"><span data-stu-id="5e91e-102">Data type(s) of the type parameter(s) cannot be inferred from these arguments</span></span>
<span data-ttu-id="5e91e-103">Типы данных параметров типа не могут выводиться из этих аргументов.</span><span class="sxs-lookup"><span data-stu-id="5e91e-103">Data type(s) of the type parameter(s) cannot be inferred from these arguments.</span></span> <span data-ttu-id="5e91e-104">Эту ошибку может исправить явное указание типов данных.</span><span class="sxs-lookup"><span data-stu-id="5e91e-104">Specifying the data type(s) explicitly might correct this error.</span></span>  
  
 <span data-ttu-id="5e91e-105">Эта ошибка возникает при неудачном разрешении перегрузки.</span><span class="sxs-lookup"><span data-stu-id="5e91e-105">This error occurs when overload resolution has failed.</span></span> <span data-ttu-id="5e91e-106">Ошибка появляется в виде сообщения, в котором указывается, почему была исключена определенная потенциальная перегрузка.</span><span class="sxs-lookup"><span data-stu-id="5e91e-106">It occurs as a subordinate message that states why a particular overload candidate has been eliminated.</span></span> <span data-ttu-id="5e91e-107">Сообщение об ошибке объясняется, что компилятор не может использовать определение типа для поиска типов данных для параметров типа.</span><span class="sxs-lookup"><span data-stu-id="5e91e-107">The error message explains that the compiler cannot use type inference to find data types for the type parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e91e-108">Когда указание аргументов является обязательным (например, в операторах выражений запросов), это сообщение об ошибке появляется без второй фразы.</span><span class="sxs-lookup"><span data-stu-id="5e91e-108">When specifying arguments is not an option (for example, for query operators in query expressions), the error message appears without the second sentence.</span></span>  
  
 <span data-ttu-id="5e91e-109">Эта ошибка демонстрируется в приведенном ниже коде.</span><span class="sxs-lookup"><span data-stu-id="5e91e-109">The following code demonstrates the error.</span></span>  
  
```vb  
Module Module1  
  
    Sub Main()  
  
        '' Not Valid.  
        'OverloadedGenericMethod("Hello", "World")  
  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T)(ByVal x As String,   
                                      ByVal y As InterfaceExample(Of T))  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,   
                                         ByVal y As InterfaceExample(Of R))  
    End Sub  
  
End Module  
  
Interface InterfaceExample(Of T)  
End Interface  
```  
  
 <span data-ttu-id="5e91e-110">**Идентификатор ошибки:** BC36647 и BC36644</span><span class="sxs-lookup"><span data-stu-id="5e91e-110">**Error ID:** BC36647 and BC36644</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5e91e-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5e91e-111">To correct this error</span></span>  
  
-   <span data-ttu-id="5e91e-112">Попробуйте указать тип данных для параметра или параметров типа, вместо того чтобы полагаться на определение типа.</span><span class="sxs-lookup"><span data-stu-id="5e91e-112">You may be able to specify a data type for the type parameter or parameters instead of relying on type inference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e91e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5e91e-113">See also</span></span>
- [<span data-ttu-id="5e91e-114">Неявное преобразование делегата</span><span class="sxs-lookup"><span data-stu-id="5e91e-114">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="5e91e-115">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e91e-115">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="5e91e-116">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e91e-116">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
