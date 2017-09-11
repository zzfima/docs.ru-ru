---
title: "Атрибут «Расширения» может применяться только к объявлениям «Модуль», «Sub» или «Функция» | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
dev_langs:
- VB
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e88241180fe1320bfd1db90a38a9a7560ae3dead
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a><span data-ttu-id="03644-102">Атрибут «Расширения» может применяться только к объявлениям «Модуль», «Sub» или «Функция»</span><span class="sxs-lookup"><span data-stu-id="03644-102">&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations</span></span>
<span data-ttu-id="03644-103">Единственный способ расширения типа данных в Visual Basic является определение метода расширения внутри стандартного модуля.</span><span class="sxs-lookup"><span data-stu-id="03644-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="03644-104">Метод расширения может быть `Sub` процедуры или `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="03644-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="03644-105">Все методы расширения должен быть помечен атрибутом расширения, `<Extension()>`, из <xref:System.Runtime.CompilerServices?displayProperty=fullName>имен.</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="03644-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="03644-106">Кроме того модуль, содержащий метод расширения может быть помечен таким же образом.</span><span class="sxs-lookup"><span data-stu-id="03644-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="03644-107">Не используется атрибут расширения является допустимым.</span><span class="sxs-lookup"><span data-stu-id="03644-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="03644-108">**Идентификатор ошибки:** BC36550</span><span class="sxs-lookup"><span data-stu-id="03644-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03644-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="03644-109">To correct this error</span></span>  
  
-   <span data-ttu-id="03644-110">Удалите атрибут расширения.</span><span class="sxs-lookup"><span data-stu-id="03644-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="03644-111">Измените расширение в качестве метода, определенного в вложенного модуля.</span><span class="sxs-lookup"><span data-stu-id="03644-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03644-112">Пример</span><span class="sxs-lookup"><span data-stu-id="03644-112">Example</span></span>  
 <span data-ttu-id="03644-113">В следующем примере определяется `Print` метод `String` тип данных.</span><span class="sxs-lookup"><span data-stu-id="03644-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="03644-114">См. также</span><span class="sxs-lookup"><span data-stu-id="03644-114">See Also</span></span>  
 <span data-ttu-id="03644-115">[Общие сведения об атрибутах](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="03644-115">[Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="03644-116"> [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) </span><span class="sxs-lookup"><span data-stu-id="03644-116"> [Extension Methods](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) </span></span>  
<span data-ttu-id="03644-117"> [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)</span><span class="sxs-lookup"><span data-stu-id="03644-117"> [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)</span></span>

