---
title: /optioncompare
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 62a9a4bf3428f3ee731e7ecc63be51dbf3076ee4
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="optioncompare"></a>/optioncompare
Задает способ сравнения строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a>Примечания  
 Можно указать `/optioncompare` в одну из двух форм: `/optioncompare:binary` использовать двоичное сравнение строк, и `/optioncompare:text` использовать текстовое сравнение строк. По умолчанию компилятор использует `/optioncompare:binary`.  
  
 В Microsoft Windows используется кодовая страница определяет двоичный порядок сортировки. Двоичный порядок сортировки выглядит следующим образом:  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Сравнение текстовых строк основано на порядок сортировки текста без учета регистра, определяемого языком вашей системы. Порядок сортировки текста обычно выглядит следующим образом:  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a>Чтобы задать дополнительные в Интегрированной среде разработки Visual Studio  
  
1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.   
  
2.  Откройте вкладку **Компиляция**.  
  
3.  Измените значение в **Option Compare** поле.  
  
### <a name="to-set-optioncompare-programmatically"></a>Чтобы установить дополнительные программными средствами  
  
-   В разделе [Option Compare-оператор](../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `ProjFile.vb` и использует двоичное сравнение строк.  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
