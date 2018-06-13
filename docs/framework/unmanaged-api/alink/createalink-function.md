---
title: Функция CreateALink
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1e29c9c246649229900beba2fcc9ab482071ae46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400670"
---
# <a name="createalink-function"></a>Функция CreateALink
Создает экземпляр компоновщика сборок и задает указатель для указанного интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`riid`|Физическое имя одного из интерфейсов компоновщика сборок.|  
|`ppInterface`|Расположение, которое при успешном завершении содержит указатель на `riid` интерфейса.|  
  
## <a name="requirements"></a>Требования  
 **Библиотека**: alink.dll  
  
## <a name="see-also"></a>См. также  
 [Al.exe (компоновщик сборок)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
