---
title: Имена объявленных типов (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 5b1f8ccc402f7f5928a33f434664b0f28d108e6d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814072"
---
# <a name="declared-element-names-visual-basic"></a>Имена объявленных типов (Visual Basic)
Каждый объявленный элемент имеет имя, также называемое *идентификатор*, который является то, что код использует для ссылки на него.  
  
## <a name="rules"></a>Правила  
 Имя элемента в Visual Basic необходимо соблюдать следующие правила:  
  
-   Он должен начинаться с буквы или символа подчеркивания (`_`).  
  
-   Оно должно содержать только буквы, десятичные цифры и знаки подчеркивания.  
  
-   Он должен содержать по крайней мере одна буква или десятичной цифрой, если он начинается с символа подчеркивания.  
  
-   Оно не должно быть более 1023 символов.  
  
 Ограничение на длину 1023 символов также применяется к всю строку полное доменное имя, например `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 В следующем примере некоторые допустимые имена элементов.  
  
 `aB123__45`  
  
 `_567`  
  
 В следующем примере некоторые недопустимые имена элементов. Первый содержит только символ подчеркивания, второй начинается с десятичным и третий содержит недопустимый символ ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  Имена элементов, начиная с символа подчеркивания (`_`) не являются частью [независимость от языка и независимые от языка компоненты](../../../../standard/language-independence-and-language-independent-components.md) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который определяет такие имена. Тем не менее символ подчеркивания в любой другой позиции в имени элемента является CLS-совместимым.  
  
### <a name="name-length-guidelines"></a>Рекомендации по длине имени  
 На практике ваши имя должно быть как можно более короткими при по-прежнему четко определять природу элемента. Это улучшает читаемость кода и сократить размер строки длины и исходного файла.  
  
 С другой стороны ваши имя не должно быть настолько коротким, что он не описывает адекватно элемент представляет и как ваш код использует его. Это важно для удобства чтения кода. Если кто-то пытается найти его, или если вы самостоятельно рассматривают его длительное время после написания, подходящие имена элементов можно сохранить значительное время.  
  
## <a name="escaped-names"></a>Дублирующие имена  
 Как правило, имя элемента не соответствовать любые ключевые слова, зарезервированные в Visual Basic, такие как `Case` или `Friend`. Тем не менее, можно определить *escape-имя*, что заключено в скобки (`[ ]`). Escape-имя может соответствовать любое слово Visual Basic, так как скобки любую неоднозначность. Скобки также используются при ссылке на имя в коде.  
  
 В общем случае следует использовать escape-имена только тогда, когда:  
  
-   Выполнена миграция кода из предыдущей версии Visual Basic, не было зарезервировано ключевого слова, используемого в качестве имени; или  
  
-   Вы работаете с кодом, написанным на другом языке, в котором заданное ключевое слово не зарезервировано.  
  
 В противном случае следует переименовать элемент, если его имя конфликтует с ключевым словом. Интегрированной среде разработки (IDE) предоставляет простой способ это сделать. Дополнительные сведения см. в разделе [Refactoring](/visualstudio/vb-ide/refactoring-vb).  
  
## <a name="case-sensitivity-in-names"></a>Учет регистра в именах  
 Имена элементов в Visual Basic регистр не учитывается. Это означает, что при сравнении двух имен, которые отличаются только регистром букв, он интерпретирует их как тем же именем. Например, он считает, что `ABC` и `abc` являются одним и тем же объявленным элементом.  
  
 Однако среда CLR (CLR) использует привязки, с учетом регистра. Таким образом, при создании сборки или DLL и предоставлении к ней доступа другим сборкам, в именах регистр учитываться не будет. Например, если определен класс с элементом `ABC`и другие сборки используют класс с помощью среды CLR, они должны ссылаться на элемент как на `ABC`. Если впоследствии перекомпилируете класс и измените имя этого элемента на `abc`, другие сборки, использующие больше не может обращаться к этому элементу. Таким образом, при выпуске обновленной версии сборки нельзя изменять регистр имен открытых элементов.  
  
## <a name="names-and-locales"></a>Имена и языковые стандарты  
 Сравнение имен не зависит от языкового стандарта. Если два имени совпадают в одном языковом стандарте, они гарантированно совпадают во всех языковых стандартах.  
  
## <a name="see-also"></a>См. также

- [Объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Операторы](../../../../visual-basic/language-reference/statements/index.md)
