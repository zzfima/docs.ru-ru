---
title: Имена объявленных типов (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ad883dd8e1de419c74b5bcdb8762994e762b4cf7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="declared-element-names-visual-basic"></a>Имена объявленных типов (Visual Basic)
Каждого объявленного элемента есть имя, также называемое *идентификатор*, которое используется код для ссылки на него.  
  
## <a name="rules"></a>Правила  
 Имя элемента в Visual Basic необходимо соблюдать следующие правила.  
  
-   Оно должно начинаться с буквы или символа подчеркивания (`_`).  
  
-   Оно должно содержать только буквы, цифры и знаки подчеркивания.  
  
-   Оно должно содержать по крайней мере одну букву, цифру или десятичный знак, если он начинается со знака подчеркивания.  
  
-   Оно не должно быть более 1023 знаков.  
  
 Ограничение на длину 1023 знаков применяется также ко всей строке полное доменное имя, например `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 В следующем примере показано некоторые допустимые имена элементов.  
  
 `aB123__45`  
  
 `_567`  
  
 В следующем примере показано некоторые недопустимые имена элементов. Первый содержит только подчеркивания, второй начинается с десятичным и третий содержит недопустимый символ ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  Имена элементов, начинающиеся с символа подчеркивания (`_`) которые не являются частью [независимость от языка и независимые от языка компоненты](../../../../standard/language-independence-and-language-independent-components.md) (CLS), поэтому CLS-совместимом коде нельзя использовать компонент, определяющий такие имена. Тем не менее символ подчеркивания в любом другом месте в имени элемента является CLS-совместимым.  
  
### <a name="name-length-guidelines"></a>Рекомендации по длине имени  
 На практике имя должно быть как можно более коротким при этом четко определять природу элемента. Это улучшает читаемость кода и уменьшает размер строки длины и исходный файл.  
  
 С другой стороны на имя не должно быть настолько коротким, что он не описывает адекватно элемент представляет и как ваш код использует. Это важно для удобства чтения кода. Если кто пытается найти его, или вы сами вернетесь к нему длительное время после их создания, подходящие имена элементов можно сохранить значительное время.  
  
## <a name="escaped-names"></a>Дублирующие имена  
 Как правило, имя элемента должно соответствует любые ключевые слова, зарезервированные в Visual Basic, такие как `Case` или `Friend`. Тем не менее, можно определить *escape-последовательность имя*, что заключено в квадратные скобки (`[ ]`). Escape-имя может совпадать любое ключевое слово Visual Basic, так как любая неопределенность в квадратные скобки. Скобки также используются при обращении к имени в коде.  
  
 В общем случае следует использовать escape-имена только если:  
  
-   Выполнена миграция кода из предыдущей версии Visual Basic, в которой не было зарезервировано ключевое слово, используемого в качестве имени; или  
  
-   Работа с кодом, написанным на другом языке, в котором данное ключевое слово не резервируется.  
  
 В противном случае следует переименовать элемент, если его имя конфликтует с зарезервированным словом. Интегрированной среды разработки (IDE) предоставляет простой способ сделать это. Дополнительные сведения см. в разделе [Refactoring](/visualstudio/vb-ide/refactoring-vb).  
  
## <a name="case-sensitivity-in-names"></a>Учет регистра в именах  
 Имена элементов в Visual Basic регистр не учитывается. Это означает, что при сравнении двух имен, которые различаются только регистром букв, он интерпретирует их как тем же именем. Например, он считает, что `ABC` и `abc` являются одним и тем же объявленным элементом.  
  
 Однако общеязыковой среды выполнения (CLR) использует привязку с учетом регистра. Таким образом, при создании сборки или DLL и предоставлении к ней доступа другим сборкам, в именах регистр учитываться не будет. Например, если определен класс с элементом `ABC`и другие сборки используют класс с помощью среды CLR, они должны ссылаться на элемент как на `ABC`. Если впоследствии перекомпилируете класс и измените имя элемента на `abc`, другие сборки, использующие больше не удалось получить доступ к этому элементу. Таким образом, при выпуске обновленной версии сборки нельзя изменять регистр имен открытых элементов.  
  
## <a name="names-and-locales"></a>Имена и языковые стандарты  
 Сравнение имен не зависит от языкового стандарта. Если два имени совпадают в одном языке, они гарантированно совпадают во всех языковых стандартах.  
  
## <a name="see-also"></a>См. также  
 [Объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Операторы](../../../../visual-basic/language-reference/statements/index.md)
