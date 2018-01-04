---
title: "Как переопределить логическое дерево"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e487220f8b06515f3d37f7d55ab7ff6214c85d92
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-override-the-logical-tree"></a>Как переопределить логическое дерево
Хотя в большинстве случаев это не требуется, разработчики улучшенных элементов управления могут переопределить логическое дерево.  
  
## <a name="example"></a>Пример  
 В этом примере описывается как подкласс <xref:System.Windows.Controls.StackPanel> переопределить логическое дерево, в этом случае для обеспечения поведения, что панель может содержать только и будет отображать только один дочерний элемент. Это поведение не является необходимым на практике, но представлено здесь, чтобы проиллюстрировать сценарий переопределения стандартного логического дерева элемента.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 Дополнительные сведения о логическом дереве см. в разделе [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).
