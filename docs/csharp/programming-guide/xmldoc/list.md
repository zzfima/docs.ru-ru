---
title: "&lt;list&gt; (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "list"
  - "<list>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<item> - XML-тег C#"
  - "<list> - XML-тег C#"
  - "<listheader> - XML-тег C#"
  - "item - XML-тег C#"
  - "list - XML-тег C#"
  - "listheader - XML-тег C#"
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# &lt;list&gt; (Руководство по программированию на C#)
## Синтаксис  
  
```  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
#### Параметры  
 `term`  
 Термин, значение которого будет определено параметром `description`.  
  
 `description`  
 Элемент маркированного или нумерованного списка, определяющий значение параметра `term`.  
  
## Заметки  
 Блок \<listheader\> служит для задания строки заголовка таблицы или списка определений.  При определении таблицы достаточно указать запись для term в заголовке.  
  
 Каждый элемент в списке указывается в блоке \<item\>.  При создании списка определений необходимо указать и `term`, и `description`.  Однако для таблицы, маркированного или нумерованного списка достаточно указать только `description`.  
  
 Список или таблица могут содержать столько блоков \<item\>, сколько необходимо.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## Пример  
 [!code-cs[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)