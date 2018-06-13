---
title: Недопустимый формат буфера обмена
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: eef16096b269902dbaca6a344abf4c5f6a504fb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586225"
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
