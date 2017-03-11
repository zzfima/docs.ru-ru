---
title: "/noconfig | Microsoft Docs"
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
  - "/noconfig - параметр компилятора [Visual Basic]"
  - "noconfig - параметр компилятора [Visual Basic]"
  - "-noconfig - параметр компилятора [Visual Basic]"
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /noconfig
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает, что компилятор не должен автоматически ссылаться на часто используемые сборки [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] или импортировать пространства имен `System` и `Microsoft.VisualBasic`.  
  
## Синтаксис  
  
```  
/noconfig  
```  
  
## Заметки  
 Параметр `/noconfig` дает компилятору команду не компилировать с использованием файла Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe.  Файл Vbc.rsp ссылается на часто используемые сборки [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] и импортирует пространства мен `System` и `Microsoft.VisualBasic`.  Компилятор неявно ссылается на сборки System.dll, если не указан параметр `/nostdlib`.  Параметр `/nostdlib` указывает компилятору не компилировать с помощью файла Vbc.rsp и не ссылаться автоматически на сборки System.dll.  
  
> [!NOTE]
>  На сборки Mscorlib.dll и Microsoft.VisualBasic.dll можно ссылаться всегда.  
  
 Можно изменить файл Vbc.rsp и указать дополнительные параметры компилятора, которые должны быть включены в каждую компиляцию Vbc.exe \(за исключением ситуаций, когда указывается параметр `/noconfig`\).  Дополнительные сведения см. в разделе [@ \(указание файла ответа\)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 Компилятор обрабатывает параметры, которые передаются команде `vbc` последними.  Таким образом любой параметр в командной строке переопределяет настройки того же параметра в файле Vbc.rsp.  
  
> [!NOTE]
>  Параметр `/noconfig` недоступен из среды разработки Visual Studio. Он доступен только при выполнении компиляции из командной строки.  
  
## См. также  
 [\/nostdlib](../../../visual-basic/reference/command-line-compiler/nostdlib.md)   
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [@ \(указание файла ответа\)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)