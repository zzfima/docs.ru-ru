---
title: Функция CoUninitializeCor
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3ce0b9a40d5375f563662d73964d28724209dcd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758290"
---
# <a name="couninitializecor-function"></a>Функция CoUninitializeCor
`CoUninitializeCor` устарел.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a>Примечания  
 Среда CLR не может быть выгружена из процесса. Чтобы полностью удалить среду выполнения из запущенного процесса, необходимо завершить работу этого процесса.  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
