---
title: "&quot;&lt;classname&gt;&quot; не является CLS-совместимым, поскольку интерфейс &quot;&lt;interfacename&gt;&quot; он реализует не является CLS-совместимым | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40029
- vbc40029
dev_langs:
- VB
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
caps.latest.revision: 13
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d2819bf2dc76291cbaf7ca9215608a11b1a98b3a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="39ltclassnamegt39-is-not-cls-compliant-because-the-interface-39ltinterfacenamegt39-it-implements-is-not-cls-compliant"></a><span data-ttu-id="7f32a-102">"&lt;classname&gt;" не является CLS-совместимым, поскольку интерфейс "&lt;interfacename&gt;" он реализует не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="7f32a-102">&#39;&lt;classname&gt;&#39; is not CLS-compliant because the interface &#39;&lt;interfacename&gt;&#39; it implements is not CLS-compliant</span></span>
<span data-ttu-id="7f32a-103">Класс или интерфейс помечен как `<CLSCompliant(True)>` , если он наследует или реализует тип, помеченный как `<CLSCompliant(False)>` или не помеченный совсем.</span><span class="sxs-lookup"><span data-stu-id="7f32a-103">A class or interface is marked as `<CLSCompliant(True)>` when it derives from or implements a type that is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="7f32a-104">Для класса или интерфейса стандарту [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS) вся его иерархия наследования должна быть совместимой.</span><span class="sxs-lookup"><span data-stu-id="7f32a-104">For a class or interface to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), its entire inheritance hierarchy must be compliant.</span></span> <span data-ttu-id="7f32a-105">Это означает, что каждый тип, от которого он наследуется прямо или косвенно, должен быть соответствующим.</span><span class="sxs-lookup"><span data-stu-id="7f32a-105">That means every type from which it inherits, directly or indirectly, must be compliant.</span></span> <span data-ttu-id="7f32a-106">Аналогично, если класс реализует один или несколько интерфейсов, то все они должны быть соответствующими по всей иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="7f32a-106">Similarly, if a class implements one or more interfaces, they must all be compliant throughout their inheritance hierarchies.</span></span>  
  
 <span data-ttu-id="7f32a-107">При применении <xref:System.CLSCompliantAttribute>к программному элементу, задайте атрибут `isCompliant` параметр либо `True` или `False` , чтобы указать соответствие или несоответствие.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="7f32a-107">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="7f32a-108">Для этого параметра нет значения по умолчанию, и вы должны предоставить его.</span><span class="sxs-lookup"><span data-stu-id="7f32a-108">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="7f32a-109">Если не применить <xref:System.CLSCompliantAttribute>на элемент, он считается как несоответствующий.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="7f32a-109">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="7f32a-110">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="7f32a-110">By default, this message is a warning.</span></span> <span data-ttu-id="7f32a-111">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="7f32a-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="7f32a-112">**Идентификатор ошибки:** BC40029</span><span class="sxs-lookup"><span data-stu-id="7f32a-112">**Error ID:** BC40029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7f32a-113">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7f32a-113">To correct this error</span></span>  
  
-   <span data-ttu-id="7f32a-114">Если требуется совместимость с CLS, определите этот тип в другой иерархии наследования или схеме реализации.</span><span class="sxs-lookup"><span data-stu-id="7f32a-114">If you require CLS compliance, define this type within a different inheritance hierarchy or implementation scheme.</span></span>  
  
-   <span data-ttu-id="7f32a-115">Если требуется, чтобы этот тип оставался в его текущей схемы иерархии или реализации наследования, удалите <xref:System.CLSCompliantAttribute>из его определения или пометьте его как `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="7f32a-115">If you require that this type remain within its current inheritance hierarchy or implementation scheme, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f32a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7f32a-116">See Also</span></span>  
 [<span data-ttu-id="7f32a-117">\<PAVE НАД настроек написание CLS-совместимого кода</span><span class="sxs-lookup"><span data-stu-id="7f32a-117">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
