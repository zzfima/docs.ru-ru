---
title: "/delaysign | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
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
  - "/delaysign - параметр компилятора [Visual Basic]"
  - "delaysign - параметр компилятора [Visual Basic]"
  - "-delaysign - параметр компилятора [Visual Basic]"
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /delaysign
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Определяет, будет ли сборка полностью или частично подписана.  
  
## Синтаксис  
  
```  
/delaysign[+ | -]  
```  
  
## Аргументы  
 `+` &#124; `-`  
 Необязательный.  Используйте `/delaysign-`, если требуется полностью подписанная сборка.  Используйте `/delaysign+`, если требуется поместить открытый ключ в сборку и зарезервировать место для хэша подписи.  Значение по умолчанию: `/delaysign-`.  
  
## Заметки  
 Опция `/delaysign` не оказывает влияния, за исключением применения с [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) или [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест \(метаданные сборки\) и подписывает хэш закрытым ключом.  Итоговая цифровая подпись хранится в файле, содержащем манифест.  При использовании отложенной подписи компилятор не вычисляет и не сохраняет подпись, а резервирует место в файле для дальнейшего добавления подписи в сборку.  
  
 Например, с помощью `/delaysign+` разработчик в организации может распространять неподписанные тестовые версии сборки, которые специалисты по тестированию могут зарегистрировать в глобальном кэше сборок и использовать.  После завершения работы по сборке лицо, ответственное за закрытый ключ организации, может полностью подписать сборку.  Это разделение ответственности защищает закрытый ключ организации от раскрытия, позволяя всем разработчикам работать со сборками.  
  
 См. раздел [Создание и использование сборок со строгими именами](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) для получения дополнительных сведений о подписи сборки.  
  
### Чтобы установить \/delaysign в среде разработки Visual Studio  
  
1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Выберите вкладку **Подпись**.  
  
3.  Установите значение в поле **Только отложенная подпись**.  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)