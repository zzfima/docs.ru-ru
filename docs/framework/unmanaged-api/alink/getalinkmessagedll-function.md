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
ms.openlocfilehash: 63719d0c6e13768e9dc7ed80e52e2a293e32a8a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449342"
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
  
## <a name="see-also"></a>См. также:

- [Al.exe (компоновщик сборок)](../../tools/al-exe-assembly-linker.md)
