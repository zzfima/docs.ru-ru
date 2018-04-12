---
title: Файл уже открыт
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3305831e840510e3f0b5bcb8bf847e39ea3ee4ba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="file-already-open"></a>Файл уже открыт
В некоторых случаях файл необходимо закрыть перед другим `FileOpen` или другую операцию. Некоторые из возможных причин этой ошибки:  
  
-   Режим последовательного вывода `FileOpen` операция была выполнена для файла, который уже открыт  
  
-   Оператор ссылается на открытый файл.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Закройте файл перед выполнением инструкции.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
