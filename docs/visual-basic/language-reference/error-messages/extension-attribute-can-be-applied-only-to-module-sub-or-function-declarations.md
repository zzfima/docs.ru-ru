---
title: '&#39;Расширение&#39; атрибут может применяться только к &#39;модуль&#39;, &#39;Sub&#39;, или &#39;функция&#39; объявления'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: d7f8829cb879d612711ac6bcc6bf4aa065fbe323
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a><span data-ttu-id="ed134-102">&#39;Расширение&#39; атрибут может применяться только к &#39;модуль&#39;, &#39;Sub&#39;, или &#39;функция&#39; объявления</span><span class="sxs-lookup"><span data-stu-id="ed134-102">&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations</span></span>
<span data-ttu-id="ed134-103">Единственный способ расширения типа данных в Visual Basic является определение метода расширения внутри стандартного модуля.</span><span class="sxs-lookup"><span data-stu-id="ed134-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="ed134-104">Методом расширения могут быть `Sub` процедуры или `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ed134-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="ed134-105">Все методы расширения должны быть помечены атрибутом расширения, `<Extension()>`, из <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ed134-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="ed134-106">При необходимости модуль, который содержит метод расширения может быть помечен таким же образом.</span><span class="sxs-lookup"><span data-stu-id="ed134-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="ed134-107">Не используется расширение атрибута является допустимым.</span><span class="sxs-lookup"><span data-stu-id="ed134-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="ed134-108">**Идентификатор ошибки:** BC36550</span><span class="sxs-lookup"><span data-stu-id="ed134-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed134-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ed134-109">To correct this error</span></span>  
  
-   <span data-ttu-id="ed134-110">Удалите атрибут расширения.</span><span class="sxs-lookup"><span data-stu-id="ed134-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="ed134-111">Измените расширение в качестве метода, определенного в вложенного модуля.</span><span class="sxs-lookup"><span data-stu-id="ed134-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed134-112">Пример</span><span class="sxs-lookup"><span data-stu-id="ed134-112">Example</span></span>  
 <span data-ttu-id="ed134-113">В следующем примере определяется `Print` метод `String` тип данных.</span><span class="sxs-lookup"><span data-stu-id="ed134-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed134-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ed134-114">See Also</span></span>  
 [<span data-ttu-id="ed134-115">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="ed134-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="ed134-116">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="ed134-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [<span data-ttu-id="ed134-117">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="ed134-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
