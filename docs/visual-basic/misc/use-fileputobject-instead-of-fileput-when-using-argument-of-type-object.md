---
title: "При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrUseFilePutObject"
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut
Метод `FilePut` включает аргумент типа`Object`. Чтобы избежать неоднозначности, следует использовать `FilePutObject` вместо `FilePut`.  
  
### Исправление ошибки  
  
-   Замените `FilePut` объектом `FilePutObject`.  
  
-   Приведите аргумент `Object` к более конкретному типу.  
  
-   Используйте функциональность объекта `My.Computer.FileSystem`.  
  
## См. также  
 [НЕ В СБОРКЕ. Функция FilePutObject](http://msdn.microsoft.com/ru-ru/a0f52a1c-5ecc-4945-b18c-03147af61d6b)   
 [Объект My.Computer.FileSystem](../../visual-basic/language-reference/objects/my-computer-filesystem-object.md)   
 [Метод My.Computer.FileSystem.WriteAllBytes](http://msdn.microsoft.com/ru-ru/b1a24dc1-eac8-4e22-8ffa-cc3bacbaf826)