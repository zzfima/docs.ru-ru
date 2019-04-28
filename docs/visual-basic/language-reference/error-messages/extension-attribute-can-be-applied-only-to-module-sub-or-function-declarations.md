---
title: Атрибут Extension может быть применен только к объявлениям Module, Sub или Function
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: a4561359e4d7cb0f6ebe44a5deb09b3374556ed8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801651"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a><span data-ttu-id="b92ec-102">Атрибут Extension может быть применен только к объявлениям Module, Sub или Function</span><span class="sxs-lookup"><span data-stu-id="b92ec-102">'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations</span></span>
<span data-ttu-id="b92ec-103">Единственный способ расширения типа данных в Visual Basic является определение метода расширения внутри стандартного модуля.</span><span class="sxs-lookup"><span data-stu-id="b92ec-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="b92ec-104">Метод расширения может быть `Sub` процедуры или `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="b92ec-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="b92ec-105">Все методы расширения должны быть помечены атрибутом расширения, `<Extension()>`, из <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b92ec-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="b92ec-106">Кроме того модуль, содержащий метод расширения может быть помечен таким же образом.</span><span class="sxs-lookup"><span data-stu-id="b92ec-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="b92ec-107">Не используется атрибут расширения является допустимым.</span><span class="sxs-lookup"><span data-stu-id="b92ec-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="b92ec-108">**Идентификатор ошибки:** BC36550</span><span class="sxs-lookup"><span data-stu-id="b92ec-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b92ec-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="b92ec-109">To correct this error</span></span>  
  
- <span data-ttu-id="b92ec-110">Удалите атрибут расширения.</span><span class="sxs-lookup"><span data-stu-id="b92ec-110">Remove the extension attribute.</span></span>  
  
- <span data-ttu-id="b92ec-111">Измените расширение в качестве метода, определенного в заключающего модуля.</span><span class="sxs-lookup"><span data-stu-id="b92ec-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b92ec-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b92ec-112">Example</span></span>  
 <span data-ttu-id="b92ec-113">В следующем примере определяется `Print` метод `String` тип данных.</span><span class="sxs-lookup"><span data-stu-id="b92ec-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b92ec-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b92ec-114">See also</span></span>

- [<span data-ttu-id="b92ec-115">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="b92ec-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="b92ec-116">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="b92ec-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="b92ec-117">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="b92ec-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
