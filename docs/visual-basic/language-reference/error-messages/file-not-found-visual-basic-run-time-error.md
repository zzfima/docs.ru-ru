---
title: "Файл не найден (Ошибка времени выполнения Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID53"
dev_langs: 
  - "VB"
ms.assetid: 57addb16-6f9a-444d-8af8-dda52431daca
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Файл не найден (Ошибка времени выполнения Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Файл не найден в указанном каталоге.  Данная ошибка могла возникнуть по следующим причинам.  
  
-   Оператор ссылается на несуществующий файл.  
  
-   Предпринята попытка вызова процедуры в динамически подключаемой библиотеке \(DLL\), но библиотека, которая указана в предложении `Lib` оператора `Declare`, не может быть найдена.  
  
-   Предпринята попытка открыть несуществующий проект или загрузить несуществующий текстовый файл.  
  
### Чтобы исправить эту ошибку  
  
1.  Проверьте правильность написания имени файла и спецификацию пути.  
  
## См. также  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)