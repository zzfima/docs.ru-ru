---
title: "Имена объявленных элементов и атрибутов (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: ed8ecf69170acf9745a4038975e7e3421722d52d
ms.lasthandoff: 03/13/2017

---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Имена объявляемых элементов и атрибутов XML (Visual Basic)
В этом разделе приведены [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] соглашения об именах элементов и атрибутов в XML-литералах XML.  В литерале XML можно указать локальное имя или полное имя. Полное имя состоит из префикса пространства имен XML, двоеточия и локального имени. Дополнительные сведения о префиксы пространства имен XML, в разделе [литерала XML элемент](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Правила  
 Локальное имя элемента или атрибута в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] должны соответствовать следующим правилам.  
  
-   Его можно начать с пространством имен. Оно должно начинаться с алфавитного символа или знака подчеркивания (`_`).  
  
-   Он должен содержать только буквы, десятичные цифры, подчеркивания, точки (.) и дефисы (-).  
  
-   Оно не должно быть более 1024 символов.  
  
-   Двоеточия, отображаемые в именах указывает разделение пространства имен. Таким образом можно использовать двоеточия только для указания пространства имен XML для определенного имени.  
  
 Кроме того следует придерживаться следующих рекомендаций.  
  
-   Спецификации XML 1.0 резервируются все имена, начинающиеся со строки «xml», любое изменение регистра символов. Таким образом не используйте эти имена для элемента и имен атрибутов.  
  
### <a name="name-length-guidelines"></a>Рекомендации по длине имени  
 На практике имя должно быть как можно более короткими, при этом четко определять природу элемента. Это улучшает читаемость кода и уменьшает размер строки длины и исходный файл.  
  
 Однако имя не должно быть настолько коротким, что оно не адекватно описывает элемент или как код использует. Это важно для удобства чтения кода. Если кто-то еще пытается разобраться, или вы сами вернетесь к нему длительное время после написания, подходящие имена элементов могут сэкономить время.  
  
## <a name="case-sensitivity-in-names"></a>Учет регистра в именах  
 Имена элементов XML учитывается регистр. Это означает, что при [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор сравнивает два имени, отличающихся только регистром буквенных, воспринимает их как разные имена. Например, он интерпретирует `ABC` и `abc` как ссылки на различные элементы.  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 При создании литерала XML-элемента, можно указать префикс пространства имен XML для имени элемента. Дополнительные сведения см. в разделе [литерала XML элемент](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>См. также  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML-литерал элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
