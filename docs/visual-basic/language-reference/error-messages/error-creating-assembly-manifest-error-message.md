---
title: "Ошибка при создании манифеста сборки: &lt;сообщениеОбОшибке&gt; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30140"
  - "vbc30140"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30140"
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Ошибка при создании манифеста сборки: &lt;сообщениеОбОшибке&gt;
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] вызывает компоновщик сборок \(Al.exe, который также называется Alink\) для создания сборки с манифестом.  Компоновщик сообщил об ошибке на этапе предварительного выпуска процедуры создания сборки.  
  
 Такая ситуация может возникнуть при наличии проблем с указанным файлом ключа или контейнером ключей.  Чтобы использовать для сборки полную подпись, необходимо предоставить допустимый файл ключа с информацией об открытом и закрытом ключах.  Чтобы использовать для сборки отложенную подпись, необходимо установить флажок **Только отложенная подпись** и предоставить допустимый файл ключа с информацией о ключах.  При использовании отложенной подписи для сборки наличие закрытого ключа не требуется.  Для получения дополнительной информации см. [How to: Sign an Assembly \(Visual Studio\)](http://msdn.microsoft.com/ru-ru/f468a7d3-234c-4353-924d-8e0ae5896564).  
  
 **Идентификатор ошибки:** BC30140  
  
### Исправление ошибки  
  
1.  Изучите приведенное сообщение об ошибке и обратитесь к разделу [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/ru-ru/7f125d49-0a03-47a6-9ba9-d61a679a7d4b), содержащему дополнительные пояснения и рекомендации по ошибке AL1019.  
  
2.  Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.  
  
## См. также  
 [How to: Sign an Assembly \(Visual Studio\)](http://msdn.microsoft.com/ru-ru/f468a7d3-234c-4353-924d-8e0ae5896564)   
 [Страница "Подписывание" в конструкторе проектов](/visual-studio/ide/reference/signing-page-project-designer)   
 [Al.exe \(компоновщик сборок\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)   
 [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/ru-ru/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Обращайтесь к нам](/visual-studio/ide/talk-to-us)