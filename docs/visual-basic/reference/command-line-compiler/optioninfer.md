---
title: "/optioninfer | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/optioninfer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/optioninfer - параметр компилятора [Visual Basic]"
  - "optioninfer - параметр компилятора [Visual Basic]"
  - "-optioninfer - параметр компилятора [Visual Basic]"
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /optioninfer
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Включает использование локального определения типов в различных объявлениях.  
  
## Синтаксис  
  
```  
/optioninfer[+ | -]  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`+`  &#124; `-`|Необязательно.  Укажите `/optioninfer+`, чтобы включить локальное определение типов, или `/optioninfer-`, чтобы заблокировать его.  Параметр `/optioninfer`, для которого не указано значение, действует так же, как `/optioninfer+`.  Значение по умолчанию при отсутствии параметра `/optioninfer` также равно `/optioninfer+`.  Значение по умолчанию задается в файле ответов Vbc.rsp.|  
  
> [!NOTE]
>  Можно использовать параметр `/noconfig`, чтобы сохранить внутренние значения компилятора по умолчанию вместо использования значений, заданных в vbc.rsp.  Значение компилятора по умолчанию для этого параметра — `/optioninfer-`.  
  
## Заметки  
 Если файл исходного кода содержит [Option Infer \- оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md), то оператор переопределяет параметр компилятора командной строки `/optioninfer`.  
  
### Чтобы задать параметр \/optioninfer в среде разработки Visual Studio  
  
1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Для получения дополнительной информации см. [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/ru-ru/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  На вкладке **Компиляция** измените значение в поле **Option infer**.  
  
## Пример  
 Следующий код компилирует `test.vb` с включенным локальным определением типов.  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Infer \- оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)   
 [Страница "Компиляция" в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)   
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)