---
title: "Файл не найден (Ошибка времени выполнения Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID53"
dev_langs: 
  - "VB"
ms.assetid: 57addb16-6f9a-444d-8af8-dda52431daca
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Файл не найден (Ошибка времени выполнения Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Файл не найден в указанном каталоге.  Данная ошибка могла возникнуть по следующим причинам.  
  
-   Оператор ссылается на несуществующий файл.  
  
-   Предпринята попытка вызова процедуры в динамически подключаемой библиотеке \(DLL\), но библиотека, которая указана в предложении `Lib` оператора `Declare`, не может быть найдена.  
  
-   Предпринята попытка открыть несуществующий проект или загрузить несуществующий текстовый файл.  
  
### Чтобы исправить эту ошибку  
  
1.  Проверьте правильность написания имени файла и спецификацию пути.  
  
## См. также  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)