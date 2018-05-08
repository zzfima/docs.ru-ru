---
title: Как переопределить логическое дерево
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: 0c7269b9ea052019e2e4f6def23b063903cbb5e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-override-the-logical-tree"></a>Как переопределить логическое дерево
Хотя в большинстве случаев это не требуется, разработчики улучшенных элементов управления могут переопределить логическое дерево.  
  
## <a name="example"></a>Пример  
 В этом примере описывается как подкласс <xref:System.Windows.Controls.StackPanel> переопределить логическое дерево, в этом случае для обеспечения поведения, что панель может содержать только и будет отображать только один дочерний элемент. Это поведение не является необходимым на практике, но представлено здесь, чтобы проиллюстрировать сценарий переопределения стандартного логического дерева элемента.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 Дополнительные сведения о логическом дереве см. в разделе [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).
