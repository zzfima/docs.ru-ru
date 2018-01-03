---
title: "Использовать &#39; FileGetObject &#39; Вместо &#39; FileGet &#39; При использовании аргумента типа &#39; объект &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 090b8088-895a-482a-9362-606596bac304
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c5be466a8a0339bdb57818755d85a26d632d774
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a>Использовать &#39; FileGetObject &#39; Вместо &#39; FileGet &#39; При использовании аргумента типа &#39; объект &#39;
Метод `FileGet` включает аргумент типа `Object`. Чтобы избежать неоднозначности, следует использовать`FileGetObject` вместо `FileGet` .  
  
 Обратите внимание, что функциональные возможности, предлагаемые `My.Computer.Filesystem` , проще в использовании и обеспечивают большую производительность, чем `FileGet` или `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Замените `FileGet` объектом `FileGetObject`.  
  
2.  Приведите аргумент `Object` к более конкретному типу.  
  
## <a name="see-also"></a>См. также  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
