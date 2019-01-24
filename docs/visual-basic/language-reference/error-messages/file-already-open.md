---
title: Файл уже открыт
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: cda72e03eb5c2469b8106957a0c50fbfa5314549
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567039"
---
# <a name="file-already-open"></a>Файл уже открыт
Иногда файл должен быть закрыт перед другим `FileOpen` или другую операцию. Некоторые из возможных причин этой ошибки:  
  
-   Режим последовательного вывода `FileOpen` операция была выполнена для файла, который уже открыт  
  
-   Оператор ссылается на открытый файл.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Закройте файл перед выполнением инструкции.  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
