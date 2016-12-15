---
title: "/keycontainer | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "/keycontainer - параметр компилятора [Visual Basic]"
  - "keycontainer - параметр компилятора [Visual Basic]"
  - "-keycontainer - параметр компилятора [Visual Basic]"
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /keycontainer
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает имя контейнера для пары ключей, чтобы дать сборке строгое имя.  
  
## Синтаксис  
  
```  
/keycontainer:container  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`container`|Обязательный.  Файл контейнера, содержащий ключ.  Заключите имя файла в кавычки \(""\), если оно содержит пробел.|  
  
## Заметки  
 Компилятор создает совместно используемый компонент, вставляя в манифест сборки открытый ключ и подписывая окончательную сборку закрытым ключом.  Чтобы создать файл ключа, введите `sn -k` `file` из командной строки.  Параметр `-i` устанавливает пару ключей в контейнере.  Дополнительные сведения см. в разделе [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md).  
  
 При компиляции с параметром `/target:module` имя файла ключей сохраняется в модуле и включается в сборку при компиляции с параметром [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Этот параметр также можно задать в качестве настраиваемого атрибута \(<xref:System.Reflection.AssemblyKeyNameAttribute>\) в исходном коде любого модуля языка MSIL.  
  
 Также можно передать сведения о шифровании компилятору с помощью [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).  Используйте [\/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md), если необходимо использовать частично подписанную сборку.  
  
 См. раздел [Создание и использование сборок со строгими именами](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) для получения дополнительных сведений о подписи сборки.  
  
> [!NOTE]
>  Параметр `/keycontainer` недоступен из среды разработки Visual Studio. Он доступен только при выполнении компиляции из командной строки.  
  
## Пример  
 В примере компилируется исходный файл `Input.vb` с указанием контейнера ключей.  
  
```  
vbc /keycontainer:key1 input.vb  
```  
  
## См. также  
 [Сборки и глобальный кэш сборок](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)