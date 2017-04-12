---
title: "/ optioninfer | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioninfer
dev_langs:
- VB
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
caps.latest.revision: 19
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
ms.openlocfilehash: 0c0b6d8361e2bd59837161d1135b100e66d40887
ms.lasthandoff: 03/13/2017

---
# <a name="optioninfer"></a>/optioninfer
Включает использование локального определения типов в различных объявлениях.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/optioninfer[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный. Укажите `/optioninfer+`, чтобы включить локальное определение типов, или `/optioninfer-`, чтобы заблокировать его. Параметр `/optioninfer`, для которого не указано значение, действует так же, как `/optioninfer+`. Значение по умолчанию при отсутствии параметра `/optioninfer` также равно `/optioninfer+`. Значение по умолчанию задается в файле ответов Vbc.rsp.|  
  
> [!NOTE]
>  Можно использовать параметр `/noconfig`, чтобы сохранить внутренние значения компилятора по умолчанию вместо использования значений, заданных в vbc.rsp. Значение компилятора по умолчанию для этого параметра — `/optioninfer-`.  
  
## <a name="remarks"></a>Примечания  
 Если файл исходного кода содержит [Option Infer оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md), то оператор переопределяет `/optioninfer` параметр компилятора командной строки.  
  
### <a name="to-set-optioninfer-in-the-visual-studio-ide"></a>Чтобы задать параметр /optioninfer в среде разработки Visual Studio  
  
1.  Выберите проект в **обозревателе решений**. На **проекта** меню, щелкните **свойства**. Дополнительные сведения см. в разделе [NIB: управление свойства проекта с помощью конструктора проектов](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  На **компиляции** измените значение в **Option infer** поле.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `test.vb` с включенным локальным определением типов.  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Дополнительные](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [Дополнительные сведения](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Диалоговое окно параметров значения по умолчанию, проекты, Visual Basic](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)   
 [Страница "Компиляция" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)   
 [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
