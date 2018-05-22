---
title: Практическое руководство. Использование специальных символов в XAML
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: c593ca094487e8f7016b02870026321fbcb9a7c3
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="how-to-use-special-characters-in-xaml"></a>Практическое руководство. Использование специальных символов в XAML
Файлы разметки, созданной в [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] автоматически сохраняются в [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] формат файла UTF-8, означающее неправильно закодирован большинство специальных символов, таких как диакритические знаки. Но существует набор широко используемых специальных символов, которые обрабатываются по-другому. Эти специальные знаки соответствуют [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] стандарту кодирования.  
  
 В следующей таблице показан синтаксис кодирования этого набора специальных символов:  
  
|Знак|Синтаксис|Описание|  
|---------------|------------|-----------------|  
|<|`&lt;`|Символ "меньше чем".|  
|>|`&gt;`|Символ "больше чем".|  
|&|`&amp;`|Символ амперсанда.|  
|"|`&quot;`|Символ двойной кавычки.|  
  
> [!NOTE]
>  При создании файла разметки с помощью текстового редактора, таких как [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] «Блокнот», необходимо сохранить файл в [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] специальные символы в кодировке UTF-8. формат файла для сохранения любых.  
  
 В приведенном ниже примере показано, как можно использовать специальные символы в тексте при создании разметки.  
  
## <a name="example"></a>Пример  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
