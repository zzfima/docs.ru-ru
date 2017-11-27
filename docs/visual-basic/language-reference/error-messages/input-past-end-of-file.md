---
title: "Оператор Input обнаружил конец файла"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 27de462d5d28ee09107d75afe8269e7401c4dc39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
