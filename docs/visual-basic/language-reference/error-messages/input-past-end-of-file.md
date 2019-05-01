---
title: Оператор Input обнаружил конец файла
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 5da14c7a28ecdcd023fc6439cb6ed64444c1183b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013794"
---
# <a name="input-past-end-of-file"></a>Оператор Input обнаружил конец файла
Либо `Input` считывает данные из файла, который является пустым или в которой все данные используются, или была использована инструкция `EOF` функцию с файл открыт для двоичного доступа.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Используйте `EOF` функции непосредственно перед `Input` инструкцию, чтобы определить конец файла.  
  
2. Если файл открыт для двоичного доступа, используйте `Seek` и `Loc`.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
