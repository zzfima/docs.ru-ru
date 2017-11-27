---
title: /optionstrict
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f783cc5b20c4fe6d7812a05a66cbc4cdfc0b9395
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="optionstrict"></a>/optionstrict
Требовать строгой семантики для ограничения неявного преобразования типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательно. `/optionstrict+` Ограничивает неявное преобразование типов. Значение по умолчанию для этого параметра — `/optionstrict-`. `/optionstrict+` Параметр совпадает со значением `/optionstrict`. Можно использовать как для разрешающей семантики.  
  
 `custom`  
 Обязательный. Предупреждать, когда не накладывается ограничение на строгую семантику языка.  
  
## <a name="remarks"></a>Примечания  
 Когда `/optionstrict+` действует, неявно могут выполняться только расширяющие преобразования типа. Неявные преобразования типов, например для присвоения `Decimal` типом объекта в объект типа integer, помечаются как ошибки.  
  
 Для создания предупреждения для неявных сужающих преобразований типа, используйте `/optionstrict:custom`. Используйте `/nowarn:numberlist` игнорировать определенных предупреждений и `/warnaserror:numberlist` обрабатывать конкретного предупреждения как ошибки.  
  
### <a name="to-set-optionstrict-in-the-visual-studio-ide"></a>Чтобы задать дополнительные сведения в Интегрированной среде разработки Visual Studio  
  
1.  Выберите проект в **Обозревателе решений**. На **проекта** меню, нажмите кнопку **свойства.** Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Откройте вкладку **Компиляция**.  
  
3.  Измените значение в **Option Strict** поле.  
  
### <a name="to-set-optionstrict-programmatically"></a>Чтобы установить/optionstrict программными средствами  
  
-   В разделе [Option Strict-оператор](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `Test.vb` с помощью строгой семантики.  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)  
 [/ warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
