---
title: "/main | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/main - параметр компилятора [Visual Basic]"
  - "main - параметр компилятора [Visual Basic]"
  - "-main - параметр компилятора [Visual Basic]"
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /main
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает класс или модуль, содержащий процедуру `Sub Main`.  
  
## Синтаксис  
  
```  
/main:location  
```  
  
## Аргументы  
 `location`  
 Обязательный.  Полное имя класса или модуля, содержащего процедуру `Sub Main`, вызываемую при запуске программы.  Это может быть в формате **\/main:module** или **\/main:namespace.module**.  
  
## Заметки  
 Следует использовать данный параметр для создания исполняемого файла или программы для Windows.  Если параметр **\/main** опущен, компилятор ищет подходящее общее значение `Sub Main` во всех открытых классах и модулях.  
  
 См. [Процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) для обзора различных форм процедуры `Main`.  
  
 Когда `location` представляет собой класс, наследуемый от <xref:System.Windows.Forms.Form>, компилятор предоставляет процедуру по умолчанию `Main`, которая запускает приложение, если класс не имеет процедуры `Main`.  Это позволяет компилировать код, который был создан в среде разработки, в командной строке.  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### Чтобы установить параметр \/main в интегрированной среде разработки Visual Studio  
  
1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  
  
     Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Перейдите на вкладку **Приложение**.  
  
3.  Убедитесь, что флажок **включить приложение Framework** не установлен.  
  
4.  Измените значение в поле **Объект запуска**.  
  
## Пример  
 Следующий код компилирует `T2.vb` и `T3.vb`, указав, что процедура `Sub Main` будет найдена в классе `Test2`.  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/ru-ru/9d030b60-e148-4366-a462-69532f02294c)   
 [Процедура Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)