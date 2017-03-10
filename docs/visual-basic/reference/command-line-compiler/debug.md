---
title: "/debug (Visual Basic) | Microsoft Docs"
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
  - "/debug - параметр компилятора [Visual Basic]"
  - "debug - параметр компилятора [Visual Basic]"
  - "-debug - параметр компилятора [Visual Basic]"
  - "отладочные ключи компилятора"
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# /debug (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает компилятору создавать отладочную информацию и помещать ее в выходной файл \(файлы\).  
  
## Синтаксис  
  
```  
/debug[+ | -]  
' -or-  
/debug:[full | pdbonly]  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`+`  &#124; `-`|Необязательный.  При задании `+` или `/debug` компилятор создает отладочную информацию и помещает ее в .pdb файл.  Указание `-` эквивалентно отсутствию указания `/debug`.|  
|`full`  &#124; `pdbonly`|Необязательный.  Указывает тип отладочной информации, создаваемой компилятором.  Если не указан `/debug:pdbonly`, то по умолчанию используется `full`, который позволяет присоединить отладчик к выполняющейся программе.  Аргумент `pdbonly` позволяет отладку исходного кода, когда программа запускается в отладчике, но ассемблерный код отображается, только когда запущенная программа присоединяется к отладчику.|  
  
## Заметки  
 Используйте эту опцию для создания отладочных версий.  Если не задать параметр `/debug`, `/debug+` или `/debug:full`, то отладка скомпилированного файла будет невозможна.  
  
 По умолчанию отладочная информация не создается \(`/debug-`\).  Для получения отладочной информации, укажите `/debug` или `/debug+`.  
  
 Сведения о настройке производительности отладки приложения содержатся в разделе [Упрощение отладки образов](../Topic/Making%20an%20Image%20Easier%20to%20Debug.md).  
  
||  
|-|  
|Чтобы установить параметр \/debug в среде разработки Visual Studio|  
|1.  Выбрав проект в **обозревателе решений**, в меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Compile**.<br />3.  Щелкните **Дополнительные параметры компиляции**.<br />4.  Измените значение в окне **Создать отладочную информацию**.|  
  
## Пример  
 Следующий пример демонстрирует размещение отладочной информации в файле `App.exe`.  
  
```  
vbc /debug /out:app.exe test.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)