---
title: "Недопустимый формат буфера обмена"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7adc417d962de35272319d7dc976b237c7e2b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="clipboard-format-is-not-valid"></a>Недопустимый формат буфера обмена
Указанный формат буфера обмена не совместим с выполняемый метод. Среди возможных причин этой ошибки являются:  
  
-   Использование буфера обмена `GetText` или `SetText` метод с форматом буфера обмена, отличным от `vbCFText` или `vbCFLink`.  
  
-   Использование буфера обмена `GetData` или `SetData` метод с форматом буфера обмена, отличным от `vbCFBitmap`, `vbCFDIB`, или `vbCFMetafile`.  
  
-   С помощью `DataObject``GetData` метода или `SetData` метод с форматом буфера обмена в диапазоне, зарезервированном Microsoft Windows для зарегистрированных форматов (& HC000 - & HFFFF), при этом формат буфера обмена не был зарегистрирован с Microsoft Windows.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите недопустимый формат и укажите допустимый.  
  
## <a name="see-also"></a>См. также  
 [Буфер обмена. Добавление других форматов](/cpp/mfc/clipboard-adding-other-formats)
