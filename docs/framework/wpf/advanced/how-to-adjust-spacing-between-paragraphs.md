---
title: "Практическое руководство. Изменение интервалов между абзацами"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b2d02e1513a0d8a3c31e4a13c9599666a4122a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a>Практическое руководство. Изменение интервалов между абзацами
В этом примере показано, как Настройка или устранение интервалов между абзацами в содержимом нефиксированного формата.  
  
 В содержимом нефиксированного формата дополнительное пространство, возникающее между абзацами является результатом поля этих абзацев. Таким образом интервала между абзацами можно управлять, настраивая размеры полей этих абзацев.  Чтобы полностью убрать дополнительное расстояние между двумя абзацами, установите поля для абзацев в **0**.  Для достижения одинакового интервала между абзацами во всем <xref:System.Windows.Documents.FlowDocument>, использовать для задания одинакового значения поля для всех абзацев в стилях <xref:System.Windows.Documents.FlowDocument>.  
  
 Это важно отметить, что поля для двух соседних абзацев будет «свернуть» большее из двух полей, а не вдвое. Таким образом Если два соседних абзаца имеют поля 20 пикселей и 40 пикселей соответственно, результирующий интервал между абзацами будет 40 пикселей, большее из двух значений полей.  
  
## <a name="example"></a>Пример  
 В следующем примере используется стили, чтобы задать поля для всех <xref:System.Windows.Documents.Paragraph> элементов в <xref:System.Windows.Documents.FlowDocument> для **0**, которая эффективно удаляет дополнительное расстояние между абзацами в <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
