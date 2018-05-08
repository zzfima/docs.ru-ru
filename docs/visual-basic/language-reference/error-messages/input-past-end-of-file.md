---
title: Оператор Input обнаружил конец файла
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: abd5f5c6e5df262d1deadd74f0a146a8d436ceb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="input-past-end-of-file"></a>Оператор Input обнаружил конец файла
Либо `Input` инструкция выполняет чтение из файла, который является пустым или в котором используются все данные, или была использована `EOF` функции с помощью файла открытого для двоичного доступа.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Используйте `EOF` работать непосредственно перед `Input` инструкцию, чтобы определить конец файла.  
  
2.  Если файл открыт для двоичного доступа, используйте `Seek` и `Loc`.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
