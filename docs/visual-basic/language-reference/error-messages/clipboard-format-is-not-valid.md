---
title: Недопустимый формат буфера обмена
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 5ec077be30b0afc8917d431dc9bd73c8dd41be89
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58817184"
---
# <a name="clipboard-format-is-not-valid"></a>Недопустимый формат буфера обмена
Указанный формат буфера обмена не совместим с выполняемый метод. Среди возможных причин этой ошибки:  
  
-   Использование буфера обмена `GetText` или `SetText` метод с формат буфера обмена, отличных от `vbCFText` или `vbCFLink`.  
  
-   Использование буфера обмена `GetData` или `SetData` метод с формат буфера обмена, отличных от `vbCFBitmap`, `vbCFDIB`, или `vbCFMetafile`.  
  
-   С помощью `GetData` или `SetData` методы `DataObject` с формат буфера обмена в диапазоне, зарезервированной с помощью Microsoft Windows для зарегистрированных форматов (& HC000 - & HFFFF), при этом формат буфера обмена не был зарегистрирован с помощью Microsoft Windows .  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите недопустимый формат и укажите допустимый.  
  
## <a name="see-also"></a>См. также

- [Буфер обмена. Добавление других форматов](/cpp/mfc/clipboard-adding-other-formats)
