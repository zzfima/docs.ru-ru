---
title: Перечисление CorFileMapping
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c8864aa604b0483130eac5aa0d7c0640abbac99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443727"
---
# <a name="corfilemapping-enumeration"></a>Перечисление CorFileMapping
Содержит значения, описывающие тип сопоставления файлов, которое возвращается из вызова [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`fmFlat`|Файл сопоставлен как файл данных. То есть `SEC_IMAGE` флаг не был передан в Microsoft Win32 `CreateFileMapping` функции.|  
|`fmExecutableImage`|Сопоставленный файл для выполнения, с помощью `LoadLibrary` функции или `CreateFileMapping` функционировать с `SEC_IMAGE` флаг.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [Метод GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
