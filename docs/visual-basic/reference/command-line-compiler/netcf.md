---
title: "/netcf | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/netcf"
  - "netcf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/netcf - параметр компилятора [Visual Basic]"
  - "netcf - параметр компилятора [Visual Basic]"
  - "-netcf - параметр компилятора [Visual Basic]"
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /netcf
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Задает компилятору целевой [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].  
  
## Синтаксис  
  
```  
/netcf  
```  
  
## Заметки  
 Параметр `/netcf` указывает компилятору [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выбрать [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] вместо полного [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  Функциональность языка, имеющаяся только в полном [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], не поддерживается.  
  
 `/netcf` параметр был разработан, чтобы использоваться с [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).  Языковые возможности, отключенные с помощью `/netcf`, совпадают с языковыми возможностями, отсутствующими в файлах при задании `/sdkpath`.  
  
> [!NOTE]
>  Параметр `/netcf` недоступен из среды разработки Visual Studio. Он доступен только при выполнении компиляции из командной строки.  Параметр `/netcf` устанавливается при загрузке проекта устройства [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Параметр `/netcf` изменяет следующие функции языка:  
  
-   Зарезервированное слово [Оператор End \<ключевое\_слово\>](../../../visual-basic/language-reference/statements/end-keyword-statement.md), которое прекращает выполнение программы, отключено.  Следующая программа компилируется и выполняется без параметра `/netcf`, но происходит сбой во время компиляции с параметром `/netcf`.  
  
     [!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   Позднее связывание во всех формах отключено.  При обнаружении сценариев с поздним связыванием создаются ошибки времени компиляции.  Следующая программа компилируется и выполняется без параметра `/netcf`, но происходит сбой во время компиляции с параметром `/netcf`.  
  
     [!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   Модификаторы [Auto](../../../visual-basic/language-reference/modifiers/auto.md) [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) и [Юникод](../../../visual-basic/language-reference/modifiers/unicode.md) отключены.  Синтаксис инструкции [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md) также изменен на `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.  Следующий пример кода демонстрирует влияние параметра `/netcf` на процесс компиляции.  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   Использование ключевых слов Visual Basic 6.0, которые были удалены из [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], создает различные ошибки при использовании `/netcf`.  Это приводит к сообщениям об ошибках при использовании следующих зарезервированных слов.  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## Пример  
 В следующем примере кода компиляция файла `Myfile.vb` с [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] выполняется с помощью библиотек mscorlib.dll и microsoft.visualbasic.dll, обнаруженных в стандартной папке установки [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] на диске С.  Как правило следует использовать самую последнюю версию [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)