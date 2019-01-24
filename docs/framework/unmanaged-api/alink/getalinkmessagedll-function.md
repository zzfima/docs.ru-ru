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
ms.openlocfilehash: 632f19e0ead57d5508265fece578bb22f18ba54a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722729"
---
# <a name="getalinkmessagedll-function"></a>Функция GetALinkMessageDll
Находит и загружает сообщения библиотеки DLL. Возвращает 0, если Библиотека сообщений не может быть расположен или загружен. Сообщение DLL должно быть либо в подкаталоге, имя которого совпадает с Идентификатором языка, либо в текущем каталоге.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** alink.h  
  
 **Библиотека**: alink.dll  
  
## <a name="see-also"></a>См. также
- [Al.exe (компоновщик сборок)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
