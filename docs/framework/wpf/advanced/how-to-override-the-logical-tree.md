---
title: Практическое руководство. Переопределение логического дерева
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: bf3459fff1a90326794d6713dd39c73596b0e960
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768450"
---
# <a name="how-to-override-the-logical-tree"></a><span data-ttu-id="65bc5-102">Практическое руководство. Переопределение логического дерева</span><span class="sxs-lookup"><span data-stu-id="65bc5-102">How to: Override the Logical Tree</span></span>
<span data-ttu-id="65bc5-103">Хотя в большинстве случаев это не требуется, разработчики улучшенных элементов управления могут переопределить логическое дерево.</span><span class="sxs-lookup"><span data-stu-id="65bc5-103">Although it is not necessary in most cases, advanced control authors have the option to override the logical tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65bc5-104">Пример</span><span class="sxs-lookup"><span data-stu-id="65bc5-104">Example</span></span>  
 <span data-ttu-id="65bc5-105">В этом примере описывается как подкласс <xref:System.Windows.Controls.StackPanel> переопределить логическое дерево, в этом случае для обеспечения поведения, что панель может иметь только и будет отображать только один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="65bc5-105">This example describes how to subclass <xref:System.Windows.Controls.StackPanel> to override the logical tree, in this case to enforce a behavior that the panel may only have and will only render a single child element.</span></span> <span data-ttu-id="65bc5-106">Это поведение не является необходимым на практике, но представлено здесь, чтобы проиллюстрировать сценарий переопределения стандартного логического дерева элемента.</span><span class="sxs-lookup"><span data-stu-id="65bc5-106">This isn't necessarily a practically desirable behavior, but is shown here as a means of illustrating the scenario for overriding an element's normal logical tree.</span></span>  
  
 [!code-csharp[LogicalOverride#SingletonPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 <span data-ttu-id="65bc5-107">Дополнительные сведения о логическом дереве см. в разделе [Деревья в WPF](trees-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="65bc5-107">For more information on the logical tree, see [Trees in WPF](trees-in-wpf.md).</span></span>
