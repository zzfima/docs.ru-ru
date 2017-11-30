---
title: "Практическое руководство. Включение обрезки текста"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimmng text
- trimmng text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8f0f24bb6271e63dc50bd063aedfd8185711e7a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-enable-text-trimming"></a>Практическое руководство. Включение обрезки текста
В этом примере демонстрируется использование и влияние значений, доступных в <xref:System.Windows.TextTrimming> перечисления.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется <xref:System.Windows.Controls.TextBlock> элемент с <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> набором атрибутов.  
  
 [!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## <a name="example"></a>Пример  
 Установив соответствующие <xref:System.Windows.TextTrimming> свойства в коде показана ниже.  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 В настоящее время три значения для усечения текста: **CharacterEllipsis**, **WordEllipsis**, и **нет**.  
  
 Когда <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> равно **CharacterEllipsis**, текст обрезается и продолжается многоточием после символа, ближайшего к краю обрезки.  Эта настройка позволяет обрезать текст максимально близко к границе обрезки, однако иногда частично обрезаются слова.  На следующем рисунке показано влияние этого параметра на <xref:System.Windows.Controls.TextBlock> аналогично указанному выше.  
  
 ![Пример: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")  
  
 Когда <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> равно **WordEllipsis**, текст обрезается и продолжается многоточием в конце первого полного слова, ближайшего к краю обрезки.  Этот параметр не будут отображаться частично обрезанные слова, но не текст обрезается так близко к краю обрезки, как **CharacterEllipsis** параметр.  На следующем рисунке показано влияние этого параметра на <xref:System.Windows.Controls.TextBlock> описанный выше.  
  
 ![Пример: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")  
  
 При <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> равно **нет**, то обрезка текста не выполняется.  В этом случае текст просто обрезается по границе родительского контейнера текста.  На следующем рисунке показано влияние этого параметра на <xref:System.Windows.Controls.TextBlock> аналогично указанному выше.  
  
 ![Пример: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")
