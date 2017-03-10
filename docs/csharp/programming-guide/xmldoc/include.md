---
title: "&lt;include&gt; (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "include"
  - "<include>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<include> - XML-тег C#"
  - "include - XML-тег C#"
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# &lt;include&gt; (Руководство по программированию на C#)
## Синтаксис  
  
```  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### Параметры  
 `filename`  
 Имя файла XML, содержащего документацию.  Имя файла может быть дополнено путем.  Заключите `filename` в одинарные кавычки \(' '\).  
  
 `tagpath`  
 Путь тегов в `filename`, который приводит к тегу `name`.  Заключите путь в одинарные кавычки \(' '\).  
  
 `name`  
 Спецификатор имени в теге, который предшествует комментариям; `name` будет иметь `id`.  
  
 `id`  
 Идентификатор для тега, который предшествует комментариям.  Заключите идентификатор в двойные кавычки \(" "\).  
  
## Заметки  
 Используйте тег \<include\> для ссылок на комментарии в другом файле, описывающем типы и элементы в исходном коде.  Это является альтернативой помещению комментариев документации непосредственно в файле исходного кода.  Поместив документацию в отдельный файл, можно применять систему управления версиями в документации отдельно от исходного кода.  Один человек может иметь извлеченный файл исходного кода, а другой — извлеченный файл документации.  
  
 Тег \<include\> использует синтаксис XPath XML.  Сведения о способах настройки использования тега \<include\> см. в документации по XPath.  
  
## Пример  
 В данном примере используется несколько файлов.  Первый файл, использующий тег \<include\>, указан ниже.  
  
 [!code-cs[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/include_1.cs)]  
  
 Второй файл — xml\_include\_tag.doc — содержит следующие комментарии к документации.  
  
```  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## Выходные данные программы  
 Следующие выходные данные создаются при компиляции классов Test и Test2 с помощью следующей командной строки: `/doc:DocFileName.xml.`. В Visual Studio параметр комментариев документации XML задается в области построения конструктора проектов.  Когда компилятор C\# находит тег \<inclue\>, он выполняет поиск комментариев документации в файле xml\_include\_tag.doc, а не в текущем исходном файле.  Затем компилятор создает файл DocFileName.xml, и этот файл используется средствами документации, такими как [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061), для создания окончательной документации.  
  
```  
<?xml version="1.0"?>   
<doc>   
    <assembly>   
        <name>xml_include_tag</name>   
    </assembly>   
    <members>   
        <member name="T:Test">   
            <summary>   
The summary for this type.   
</summary>   
        </member>   
        <member name="T:Test2">   
            <summary>   
The summary for this other type.   
</summary>   
        </member>   
    </members>   
</doc>   
```  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)