---
title: "Практическое руководство. Использование специальных символов в XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "знаки, особый"
  - "специальные символы"
  - "оформление, специальные символы"
  - "Юникод UTF-8 - формат файлов"
  - "UTF-8 - формат файлов"
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# Практическое руководство. Использование специальных символов в XAML
Файлы разметки, которые создаются в среде [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] автоматически сохраняются в файловом формате [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF\-8; это означает, что большинство специальных символов, таких как знаки ударения, кодируются правильно.  Однако существует набор широко используемых специальных символов, которые обрабатываются по\-другому.  Эти специальные знаки соответствуют стандарту кодирования [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  
  
 В следующей таблице показан синтаксис кодирования этого набора специальных символов:  
  
|Знак|Синтаксис|Описание|  
|----------|---------------|--------------|  
|\<|`<`|Меньше, чем символ.|  
|\>|`>`|Больше, чем символ.|  
|&|`&`|Символ амперсанда.|  
|"|`"`|Символ двойной кавычки.|  
  
> [!NOTE]
>  При создании файла разметки с помощью текстового редактора, например, Блокнота [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], необходимо сохранить файл в формате UTF\-8 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)], чтобы сохранить кодированные специальные символы.  
  
 В следующем примере показано, как можно использовать специальные символы в тексте при создании разметки.  
  
## Пример  
 [!code-xml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]