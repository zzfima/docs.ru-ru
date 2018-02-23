---
title: "Практическое руководство. Создать простой привязки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a595f255b014e08b4b5b2036a7b1940e46df268f
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2018
---
# <a name="how-to-create-a-simple-binding"></a>Практическое руководство. Создать простой привязки
В этом примере показано, как создать простой <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Пример  
 В этом примере имеется `Person` объект с строковое свойство с именем `PersonName`. `Person` Объект определен в пространстве имен `SDKSample`.  
  
 Выделенная строка, содержащий `<src>` элемент в следующем примере создается экземпляр `Person` объекта с `PersonName` значение свойства `Joe`. Это можно сделать в `Resources` статьи и назначены `x:Key`.  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Выделенная строка, содержащий `<TextBlock>` привязывается элемент <xref:System.Windows.Controls.TextBlock> управления `PersonName` свойство. В результате <xref:System.Windows.Controls.TextBlock> имеет значение «Joe».  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
