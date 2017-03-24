---
title: "Имена объявленных элементов (Visual Basic) | Документы Microsoft"
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
- declared elements, case sensitivity
- names, Visual Basic rules
- naming conventions
- element names
- declared elements, identifiers
- declarations, elements
- declared elements, valid names
- '[] escape characters [Visual Basic]'
- names, elements
- declaration statements, declared elements
- declaring elements
- identifiers, declared elements
- case sensitivity, declared element names
- escape characters
- names, declared elements
- declared elements, about declared elements
- escaped names
- declared elements, names
- names, naming conventions
- identifiers, elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: 27
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
ms.openlocfilehash: 56ac0684e5176f33aa6f9600f20d9fe3fcf09416
ms.lasthandoff: 03/13/2017

---
# <a name="declared-element-names-visual-basic"></a>Имена объявленных типов (Visual Basic)
У каждого объявленного элемента есть имя, также называемое *идентификатор*, которое используется код для ссылки на него.  
  
## <a name="rules"></a>Правила  
 Имя элемента в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] необходимо соблюдать следующие правила:  
  
-   Оно должно начинаться с буквы или символа подчеркивания (`_`).  
  
-   Оно должно содержать только буквенные символы, десятичные цифры и знаки подчеркивания.  
  
-   Он должен содержать по крайней мере один символ латинского алфавита или десятичной цифрой, если оно начинается со знака подчеркивания.  
  
-   Оно не должно быть более 1023 знаков.  
  
 Ограничение на длину 1023 знаков применяется также ко всей строке полного имени, например `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 В следующем примере показано некоторые допустимые имена элементов.  
  
 `aB123__45`  
  
 `_567`  
  
 В следующем примере показано некоторые недопустимые имена элементов. Первый содержит только подчеркивания, второй начинается с десятичной цифры и третий содержит недопустимый символ ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  Имена элементов, начинающиеся со знака подчеркивания (`_`) не являются частью [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), поэтому в CLS-совместимом коде нельзя использовать компонент, определяющий такие имена. Тем не менее символа подчеркивания в любом другом месте в имени элемента является CLS-совместимым.  
  
### <a name="name-length-guidelines"></a>Рекомендации по длине имени  
 На практике имя должно быть как можно более короткими при этом четко определять природу элемента. Это улучшает читаемость кода и уменьшает размер строки длины и исходный файл.  
  
 С другой стороны имя необходимо настолько коротким, что оно неадекватно описывает элемент представляет и как код использует его. Это важно для удобства чтения кода. Если кто-то еще пытается разобраться, или вы сами вернетесь к нему длительное время после написания, подходящие имена элементов можно сохранить значительное время.  
  
## <a name="escaped-names"></a>Дублирующие имена  
 Как правило, имя элемента должно соответствует любое из ключевых слов, зарезервированных в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], такие как `Case` или `Friend`. Тем не менее, можно определить *escape-последовательность имя*, что заключено в скобки (`[ ]`). Escape-имя может совпадать с любым [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ключевое слово, так как скобки исключают неопределенность. Скобки также используются при обращении к этому имени в коде.  
  
 В общем случае следует использовать escape-имена только если:  
  
-   Выполнена миграция кода из предыдущей версии [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не было зарезервировано ключевое слово используемое в качестве имени; или  
  
-   Работа с кодом, написанным на другом языке, в котором заданное ключевое слово не зарезервировано.  
  
 В противном случае следует переименовать элемент, если его имя конфликтует с ключевым словом. Интегрированную среду разработки (IDE) предоставляет простой способ сделать это. Дополнительные сведения см. в разделе [Refactoring](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb).  
  
## <a name="case-sensitivity-in-names"></a>Учет регистра в именах  
 В именах элементов [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] регистр не учитывается. Это означает, что при сравнении двух имен, которые различаются только регистром буквенных символов, компилятор воспринимает их как тем же именем. Например, он считает, что `ABC` и `abc` являются одним и тем же объявленным элементом.  
  
 Однако общеязыковая среда выполнения (CLR) использует привязку с учетом регистра. Таким образом, при создании сборки или DLL и предоставлении к ней доступа другим сборкам, в именах регистр учитываться не будет. Например, если определен класс с элементом `ABC`и другие сборки используют класс с помощью среды CLR, они должны ссылаться на элемент как на `ABC`. Если впоследствии перекомпиляции класса и измените имя элемента на `abc`, другие сборки, использующие больше не удалось получить доступ к этому элементу. Таким образом, при выпуске обновленной версии сборки нельзя изменять регистр имен открытых элементов.  
  
## <a name="names-and-locales"></a>Имена и языковые стандарты  
 Сравнение имен не зависит от языкового стандарта. Если два имени совпадают в одном языке, они гарантированно совпадают во всех языковых стандартах.  
  
## <a name="see-also"></a>См. также  
 [Объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)   
 [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Операторы](../../../../visual-basic/language-reference/statements/index.md)
