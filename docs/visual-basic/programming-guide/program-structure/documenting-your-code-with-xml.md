---
title: "Документирование кода с помощью XML (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "код Visual Basic, документирование с XML"
  - "XML-комментарии, Visual Basic"
  - "XML, документирующий код"
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Документирование кода с помощью XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

В [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] можно документировать код с помощью XML  
  
## Комментарии к XML\-документации  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] предоставляет простой способ автоматического создания XML–документации для проектов.  Можно автоматически создавать XML–схему для типов и членов, а затем можно указать сводку, описательную документацию для каждого параметра и другие примечания.  С соответствующей настройкой XML–документация автоматически генерируется в XML–файл с тем же именем, что и проект, и расширением XML.  Дополнительные сведения см. в разделе [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
 XML–файл можно использовать или обрабатывать каким–либо иным способом.  Этот файл расположен в том же каталоге, что и выходные файлы EXE или DLL проекта.  
  
 XML–документация начинается с `'''`.  Обработка этих комментариев имеет некоторые ограничения:  
  
-   Документация должна представлять собой XML с правильным форматом.  Если XML не имеет правильный формат, выдается предупреждение и файл документации будет содержать комментарий о том, что произошла ошибка.  
  
-   Разработчики могут создавать свои собственные наборы тегов.  Здесь представлен рекомендуемый набор тегов \(см. "Дополнительные сведения" в этом разделе\).  Некоторые рекомендуемые теги имеют специальное значение.  
  
    -   Тег \<param\> используется для описания параметров.  При его использовании компилятор должен убедиться в том, что параметр существует и что все параметры описаны в документации.  При сбое проверки компилятор выдает предупреждение.  
  
    -   Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода.  Компилятор проверяет, что этот элемент кода существует.  При сбое проверки компилятор выдает предупреждение.  Компилятор также соблюдает любые операторы `Imports` при поиске типа, описанного в атрибуте `cref`.  
  
    -   Тег \<summary\> используется технологией IntelliSense в [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] для отображения дополнительных сведений о типе или элементе.  
  
## Связанные разделы  
 Дополнительные сведения о создании файла XML с комментариями документации содержатся в следующих разделах:  
  
-   [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [Обработка XML\-файла](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [Практическое руководство. Создание XML\-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [Средства XML в Visual Studio](/visual-studio/xml-tools/xml-tools-in-visual-studio)  
  
## См. также  
 [Разработка приложений в Visual Basic](../../../visual-basic/developing-apps/index.md)   
 [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)