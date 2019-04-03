---
title: Файл уже открыт
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: e565dbd6352a8f76290f3f58d62e2e14a18ef45f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823510"
---
# <a name="file-already-open"></a>Файл уже открыт
Иногда файл должен быть закрыт перед другим `FileOpen` или другую операцию. Некоторые из возможных причин этой ошибки:  
  
-   Режим последовательного вывода `FileOpen` операция была выполнена для файла, который уже открыт  
  
-   Оператор ссылается на открытый файл.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Закройте файл перед выполнением инструкции.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
