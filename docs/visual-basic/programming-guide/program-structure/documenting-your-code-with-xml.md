---
title: "Документирование кода с помощью XML (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML, documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2ec4907ff96a0861f97de21bdf45662c558d0a95
ms.lasthandoff: 03/13/2017

---
# <a name="documenting-your-code-with-xml-visual-basic"></a>Документирование кода с помощью XML (Visual Basic)
В [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], можно документировать код с помощью XML  
  
## <a name="xml-documentation-comments"></a>Комментарии к XML-документации  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет простой способ автоматического создания XML-документации для проектов. Можно автоматически создавать XML – схему для типов и членов, а затем можно указать сводку, описательную документацию для каждого параметра и другие примечания. С соответствующей настройкой автоматически создается XML-документации в XML-файл с тем же именем, как проект и расширением XML. Дополнительные сведения см. в разделе [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
 XML-файл можно использовать или обрабатываться как XML. Этот файл находится в том же каталоге, что и выходной файл .exe или .dll проекта.  
  
 XML – документация начинается с `'''`. Обработка этих комментариев имеет некоторые ограничения:  
  
-   Документация должен иметь правильный формат XML. Если XML не имеет правильного формата, выдается предупреждение и файл документации содержит комментарий о том, что произошла ошибка.  
  
-   Разработчики могут создавать свои собственные наборы тегов. Существует рекомендуемый набор тегов (см. «Связанные разделы» в этом разделе). Некоторые Рекомендуемые теги имеют специальное значение:  
  
    -   \<Param настроек тег используется для описания параметров. Если используется, компилятор проверит, что параметр существует и что все параметры описаны в документации. При сбое проверки компилятор выдает предупреждение.  
  
    -   `cref` Атрибута можно прикрепить к любому тегу для предоставления ссылки на элемент кода. Компилятор проверяет, что этот элемент кода существует. При сбое проверки компилятор выдает предупреждение. Компилятор также соблюдает любые `Imports` при поиске типа, описанного в инструкциях `cref` атрибута.  
  
    -   \<Сводка настроек тег используется технологией IntelliSense в [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] для отображения дополнительных сведений о тип или член.  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения о создании файла XML с комментариями документации в следующих разделах:  
  
-   [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [Обработка XML-файла](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [Средства XML в Visual Studio](https://docs.microsoft.com/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a>См. также  
 [Разработка приложений с помощью Visual Basic](../../../visual-basic/developing-apps/index.md)   
 [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)
