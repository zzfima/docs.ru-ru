---
title: "Практическое руководство. Создание XML-документации в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML-комментарии"
  - "документация XML, создание"
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Создание XML-документации в Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом примере демонстрируется добавление комментариев XML\-документации в код.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Создание XML\-документации для типа или члена  
  
1.  В **редакторе кода** поместите курсор на одну строку выше типа или члена, для которого требуется создать документацию.  
  
2.  Введите `'''` \(три знака одинарных кавычек\).  
  
     Схема XML для типа или члена добавляется в **редактор кода**.  
  
3.  Добавьте описательные сведения между соответствующими тегами.  
  
    > [!NOTE]
    >  Чтобы добавить дополнительные строки внутри блока XML\-документации, следует начинать каждую строку с кавычек `'''`.  
  
4.  Добавьте дополнительный код, который использует тип или член с новыми комментариями XML\-документации.  
  
     IntelliSense отображает текст из тега \<summary\> для типа или члена.  
  
5.  Скомпилируйте код для создания XML\-файла, содержащего комментарии документации.  Дополнительные сведения см. в разделе [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## См. также  
 [Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)   
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)