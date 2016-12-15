---
title: "/doc | Microsoft Docs"
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
  - "/doc - параметр компилятора [Visual Basic]"
  - "doc - параметр компилятора [Visual Basic]"
  - "-doc - параметр компилятора [Visual Basic]"
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /doc
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Обрабатывает комментарии для документации и помещает их в XML\-файл.  
  
## Синтаксис  
  
```  
/doc[+ | -]  
' -or-  
/doc:file  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`+`  &#124; `-`|Необязательный.  Указание \+ или просто `/doc` указывает компилятору сгенерировать сведения о документации и поместить их в XML\-файл.  Указание `-` является эквивалентом неуказанного `/doc`, не вызывает создание сведений о документации.|  
|`file`|Обязателен, если используется `/doc:`.  Задает выходной файл XML, который заполняется комментариями из файлов исходного кода компиляции.  Если имя файла содержит пробелы, заключайте имя в кавычки \(" "\).|  
  
## Заметки  
 Параметр `/doc` указывает, создавать ли компилятору XML\-файл, содержащий комментарии документации.  Если используется синтаксис `/doc:``file`, параметр `file` задает имя XML\-файла.  Если используется `/doc` или `/doc+`, компилятор принимает имя XML\-файла из исполняемого файла или библиотеки, создаваемой компилятором.  При использовании `/doc-` или, если параметр `/doc` не задан, компилятор не создает XML\-файл.  
  
 В файлах исходного кода комментариям документации могут предшествовать следующие определения.  
  
-   Определяемые пользователем типы, например [class](../../../visual-basic/language-reference/statements/class-statement.md) или [interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Члены, такие как поле, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md) или [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Чтобы использовать созданный [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] XML\-файл при помощи функции [IntelliSense](/visual-studio/ide/using-intellisense), имя XML\-файла должно совпадать с именем сборки, для которой требуется поддержка.  Убедитесь, что XML\-файл находится в той же папке, что сборка, таким образом, чтобы при ссылке на сборку в проекте [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] XML\-файл был найден.  XML\-файлы документации не требуются IntelliSense для работы с кодом в проекте или в проектах, на которые ссылается проект.  
  
 Если при компиляции не указать `/target:module`, то XML\-файл будет содержать теги `<assembly></assembly>`.  Эти теги указывают имя файла, содержащего манифест сборки для выходного файла компиляции.  
  
 Дополнительные сведения о способах создания документации из комментариев в коде см. [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).  
  
||  
|-|  
|Установка параметра \/doc в интегрированной среде разработки Visual Studio|  
|1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Compile**.<br />3.  Задайте значение в поле **Создать XML\-файл документации**.|  
  
## Пример  
 Пример см. в разделе [Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md).  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)