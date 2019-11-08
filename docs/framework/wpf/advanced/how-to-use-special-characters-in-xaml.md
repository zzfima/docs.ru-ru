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
ms.openlocfilehash: 59449637bb45f6b75462b6809c354af7972fc2e7
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740841"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Практическое руководство. Использование специальных символов в XAML
Файлы разметки, созданные в Visual Studio, автоматически сохраняются в формате Юникода UTF-8, что означает, что большинство специальных символов, таких как диакритические знаки, кодируются правильно. Но существует набор широко используемых специальных символов, которые обрабатываются по-другому. Эти специальные символы соответствуют стандарту XML для кодирования консорциум W3C (W3C).  
  
 В следующей таблице показан синтаксис кодирования этого набора специальных символов:  
  
|Знак|Синтаксис|Описание|  
|---------------|------------|-----------------|  
|<|`&lt;`|Символ "меньше чем".|  
|>|`&gt;`|Символ "больше чем".|  
|&|`&amp;`|Символ амперсанда.|  
|"|`&quot;`|Символ двойной кавычки.|  
  
> [!NOTE]
> При создании файла разметки с помощью текстового редактора, например Блокнота Windows, необходимо сохранить файл в формате Юникода UTF-8, чтобы сохранить закодированные специальные символы.  
  
 В приведенном ниже примере показано, как можно использовать специальные символы в тексте при создании разметки.  
  
## <a name="example"></a>Пример  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
