---
title: "/keyfile | Microsoft Docs"
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
  - "/keyfile - параметр компилятора [Visual Basic]"
  - "keyfile - параметр компилятора [Visual Basic]"
  - "-keyfile - параметр компилятора [Visual Basic]"
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /keyfile
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает файл, содержащий ключ или пару ключей для создания строгого имени сборки.  
  
## Синтаксис  
  
```  
/keyfile:file  
```  
  
## Аргументы  
 `file`  
 Обязательный.  Имя файла, содержащего ключ.  Заключите имя файла в кавычки \(" "\), если оно содержит пробел.  
  
## Заметки  
 Компилятор вставляет открытый ключ в манифест сборки и затем подписывает финальную сборку закрытым ключом.  Чтобы создать файл ключа, введите `sn -k file` из командной строки.  Дополнительные сведения см. в разделе [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md).  
  
 При компиляции с параметром `/target:module` имя файла ключей сохраняется в модуле и включается в сборку при компиляции с параметром [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Также можно передать сведения о шифровании компилятору с помощью [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  Используйте [\/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md), если необходимо использовать частично подписанную сборку.  
  
 Этот параметр также допускается указывать в качестве пользовательского атрибута \(<xref:System.Reflection.AssemblyKeyFileAttribute>\) в исходном коде любого модуля промежуточного языка корпорации Майкрософт.  
  
 Если параметры `/keyfile` и [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) заданы одновременно для одной и той же процедуры компиляции \(в командной строке или с помощью пользовательских атрибутов\), сначала будет предпринята попытка использования контейнера ключей.  В случае успеха сборка подписывается данными контейнера ключей.  Если контейнер ключей не обнаружен, будет предпринята попытка использовать файл, заданный параметром `/keyfile`.  В случае успеха сборка подписывается данными из файла ключей, а сведения о ключах будут помещены в контейнер ключей \(аналогично команде `sn -i`\). Таким образом, при следующей компиляции контейнер ключей будет действительным.  
  
 Обратите внимание, что файл ключей может содержать только открытый ключ.  
  
 См. раздел [Создание и использование сборок со строгими именами](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) для получения дополнительных сведений о подписи сборки.  
  
> [!NOTE]
>  Параметр `/keyfile` недоступен из среды разработки [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]; он доступен только при компиляции из командной строки.  
  
## Пример  
 В примере компилируется исходный файл `Input.vb` с указанием файла ключей.  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## См. также  
 [Сборки и глобальный кэш сборок](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)