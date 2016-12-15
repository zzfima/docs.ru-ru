---
title: "/nostdlib (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/nostdlib - параметр компилятора [Visual Basic]"
  - "nostdlib - параметр компилятора [Visual Basic]"
  - "-nostdlib - параметр компилятора [Visual Basic]"
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /nostdlib (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает компилятору не ссылаться на стандартные библиотеки автоматически.  
  
## Синтаксис  
  
```  
/nostdlib  
```  
  
## Заметки  
 Параметр `/nostdlib` удаляет автоматическую ссылку на сборку System.dll и запрещает компилятору считывание из файла VBC.RSP.  Файл Vbc.rsp, который находится в том же каталоге, что файл vbc.exe, ссылается на часто используемые сборки [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] и импортирует пространства имен `System` и `Microsoft.VisualBasic`.  
  
> [!NOTE]
>  На сборки Mscorlib.dll и Microsoft.VisualBasic.dll можно ссылаться всегда.  
  
> [!NOTE]
>  Параметр `/nostdlib` недоступен из среды разработки Visual Studio. Он доступен только при выполнении компиляции из командной строки.  
  
## Пример  
 В следующем примере компилируется файл `T2.vb` без ссылок на стандартные библиотеки.  Необходимо задать константу условной компиляции `_MYTYPE` в пустой строке, чтобы удалить объект `My`.  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## См. также  
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)