---
title: Функция GetALinkMessageDll
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 323e53c45a26d5703548ebe9863978f6d3929f0b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787481"
---
# <a name="getalinkmessagedll-function"></a>Функция GetALinkMessageDll
Находит и загружает библиотеку DLL сообщений. Возвращает 0, если не удалось обнаружить или загрузить библиотеку DLL сообщений. DLL сообщения должна быть либо в подкаталоге, имя которого является ИДЕНТИФИКАТОРом языка, либо в текущем каталоге.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ALink. h  
  
 **Библиотека**: ALink. dll  
  
## <a name="see-also"></a>См. также

- [Al.exe (компоновщик сборок)](../../tools/al-exe-assembly-linker.md)
