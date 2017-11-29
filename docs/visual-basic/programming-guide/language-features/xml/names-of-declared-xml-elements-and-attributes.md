---
title: "Имена объявляемых элементов и атрибутов XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 846a028e076873d1978f751fdb70e93c7c6a81af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Имена объявляемых элементов и атрибутов XML (Visual Basic)
Этот раздел содержит [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] соглашения об именах элементов и атрибутов в XML-литералах XML.  В литерале XML можно указать локальное имя или полное имя. Полное имя состоит из префикса пространства имен XML, двоеточия и локального имени. Дополнительные сведения о префиксы пространства имен XML см. в разделе [литерала элемента XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Правила  
 Локальное имя элемента или атрибута в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] должен соответствовать следующим правилам.  
  
-   Оно может начинаться с пространством имен. Оно должно начинаться с алфавитного символа или знака подчеркивания (`_`).  
  
-   Он должен содержать только буквы, десятичные цифры, подчеркивания, точки (.) и дефисы (-).  
  
-   Оно не должно быть более 1024 символов.  
  
-   Двоеточия, отображаемые в именах указывает разделение пространства имен. Таким образом можно использовать двоеточия только для указания пространства имен XML для определенного имени.  
  
 Кроме того необходимо придерживаться следующих рекомендаций.  
  
-   Спецификации XML 1.0 резервируются все имена, начинающиеся со строки «xml», любое изменение капитализации. Следовательно не рекомендуется использовать эти имена для элемента и имен атрибутов.  
  
### <a name="name-length-guidelines"></a>Рекомендации по длине имени  
 На практике имя должно быть как можно более коротким, при этом четко определять природу элемента. Это улучшает читаемость кода и уменьшает размер строки длины и исходный файл.  
  
 Однако ваше имя не должно быть настолько коротким, что он не описывает адекватно элемент или как код использует. Это важно для удобства чтения кода. Если кто пытается найти его, или вы сами вернетесь к нему длительное время после их создания, подходящие имена элементов могут сэкономить время.  
  
## <a name="case-sensitivity-in-names"></a>Учет регистра в именах  
 Имена элементов XML учитывается регистр символов. Это означает, что при [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] компилятора сравнивает два имени, отличающихся только регистром буквенных, интерпретирует их как разные имена. Например, он интерпретирует `ABC` и `abc` как ссылки на различные элементы.  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 При создании литерала XML-элемента, можно указать префикс пространства имен XML для имени элемента. Дополнительные сведения см. в разделе [литерала элемента XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>См. также  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML-литерал элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
