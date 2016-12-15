---
title: "Требуется объект (Visual Basic) | Microsoft Docs"
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
  - "vbrID424"
dev_langs: 
  - "VB"
ms.assetid: afdc660b-81a5-4c92-ac7e-9c3a3105fc16
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Требуется объект (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Для ссылки на свойства и методы, как правило, требуется наличие явного квалификатора объекта.  В данном случае требуется такой квалификатор.  
  
### Чтобы исправить эту ошибку  
  
1.  Проверьте, что ссылки на метод или свойство объекта имеют допустимый квалификатор объекта.  Если квалификатор объекта не указан, следует его указать.  
  
2.  Проверьте правильность написания квалификатора объекта и убедитесь, что объект является видимым в той части программы, в которой содержится ссылка на него.  
  
3.  Если указан путь к команде **File Open** ведущего приложения, проверьте правильность указанных в пути аргументов.  
  
4.  Просмотрите документацию объекта и убедитесь, что действие является допустимым.  
  
## См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)