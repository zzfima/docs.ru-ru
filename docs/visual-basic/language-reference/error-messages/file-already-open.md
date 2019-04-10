---
title: Файл уже открыт
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 401801c7c9072ce11f9eafdb84f2b377669ae545
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301325"
---
# <a name="file-already-open"></a>Файл уже открыт
Иногда файл должен быть закрыт перед другим `FileOpen` или другую операцию. Некоторые из возможных причин этой ошибки:  
  
-   Режим последовательного вывода `FileOpen` операция была выполнена для файла, который уже открыт  
  
-   Оператор ссылается на открытый файл.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Закройте файл перед выполнением инструкции.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
