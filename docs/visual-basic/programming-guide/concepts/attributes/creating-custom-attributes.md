---
title: "Создание настраиваемых атрибутов (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fbfc3f84f6287d233d475f01869dab63b937a521
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="creating-custom-attributes-visual-basic"></a><span data-ttu-id="0c9f9-102">Создание настраиваемых атрибутов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c9f9-102">Creating Custom Attributes (Visual Basic)</span></span>
<span data-ttu-id="0c9f9-103">Можно создать собственные настраиваемые атрибуты, определив класс атрибута, прямо или косвенно наследует класс <xref:System.Attribute>, делает определение определений атрибутов в метаданных и быстро.</xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="0c9f9-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="0c9f9-104">Предположим, что требуется тег типов с именем программиста, который разработал его.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="0c9f9-105">Можно определить пользовательский `Author` класса атрибута:</span><span class="sxs-lookup"><span data-stu-id="0c9f9-105">You might define a custom `Author` attribute class:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
        version = 1.0  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="0c9f9-106">Имя класса — имя атрибута `Author`.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="0c9f9-107">Он является производным от `System.Attribute`, поэтому класс настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="0c9f9-108">Параметры конструктора являются позиционными параметрами настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="0c9f9-109">В этом примере `name` является позиционным параметром.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="0c9f9-110">Все открытые поля чтения и записи или свойства являются именованными параметрами.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="0c9f9-111">В этом случае `version` только именем параметра.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="0c9f9-112">Обратите внимание на использование `AttributeUsage` атрибута `Author` атрибут допустим только для класса и `Structure` объявления.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `Structure` declarations.</span></span>  
  
 <span data-ttu-id="0c9f9-113">Этот атрибут можно использовать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0c9f9-113">You could use this new attribute as follows:</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 <span data-ttu-id="0c9f9-114">`AttributeUsage`имеет именованный параметр, `AllowMultiple`, с помощью которой можно изменять пользовательский атрибут однократного использования или multiuse.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="0c9f9-115">В следующем примере кода создается многократно используемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 <span data-ttu-id="0c9f9-116">В следующем примере несколько атрибутов одного типа применяются к классу.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
>  <span data-ttu-id="0c9f9-117">Если класс атрибута содержит свойство, что свойство должно быть чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-117">If your attribute class contains a property, that property must be read-write.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c9f9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0c9f9-118">See Also</span></span>  
 <span data-ttu-id="0c9f9-119"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="0c9f9-119"><xref:System.Reflection></span></span>   
<span data-ttu-id="0c9f9-120"> [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0c9f9-120"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="0c9f9-121"> [Написание настраиваемых атрибутов](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc) </span><span class="sxs-lookup"><span data-stu-id="0c9f9-121"> [Writing Custom Attributes](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc) </span></span>  
<span data-ttu-id="0c9f9-122"> [Отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="0c9f9-122"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="0c9f9-123"> [Атрибуты (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="0c9f9-123"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="0c9f9-124"> [Доступ к атрибутам с помощью отражения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) </span><span class="sxs-lookup"><span data-stu-id="0c9f9-124"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) </span></span>  
<span data-ttu-id="0c9f9-125"> [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)</span><span class="sxs-lookup"><span data-stu-id="0c9f9-125"> [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)</span></span>
