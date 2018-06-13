---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1906710ef10634187782f9355146dfa7ccb7748
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653407"
---
# <a name="-optioncompare"></a>-optioncompare
Задает способ сравнения строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a>Примечания  
 Можно указать `-optioncompare` в одну из двух форм: `-optioncompare:binary` использовать двоичное сравнение строк, и `-optioncompare:text` использовать текстовое сравнение строк. По умолчанию компилятор использует `-optioncompare:binary`.  
  
 В Microsoft Windows текущая кодовая страница определяет двоичный порядок сортировки. Двоичный порядок сортировки выглядит следующим образом:  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Сравнение текстовых строк основано на порядок сортировки текста без учета регистра, определяемого языком вашей системы. Порядок сортировки текста обычно выглядит следующим образом:  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a>Чтобы задать - optioncompare в Интегрированной среде разработки Visual Studio  
  
1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.   
  
2.  Откройте вкладку **Компиляция**.  
  
3.  Измените значение в **Option Compare** поле.  
  
### <a name="to-set--optioncompare-programmatically"></a>Установка - optioncompare программным способом  
  
-   В разделе [Option Compare-оператор](../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `ProjFile.vb` и использует двоичное сравнение строк.  
  
```console
vbc -optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
