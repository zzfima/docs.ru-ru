---
title: Перечисление CorPEKind
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ab94bf7c55d4c19a4f3672ed86808575b8a2239
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536923"
---
# <a name="corpekind-enumeration"></a>Перечисление CorPEKind
Содержит значения, описывающие переносимый исполняемый (PE) файл, возвращенный из вызова [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`peNot`|Указывает, что это не в PE-файл.|  
|`peILOnly`|Указывает, что этот PE-файл содержит только управляемый код.|  
|`pe32BitRequired`|Указывает, что этот PE-файл выполняет вызовы Win32.|  
|`pe32Plus`|Указывает, что этот файл PE запускается в 64-разрядной платформе.|  
|`pe32Unmanaged`|Указывает, что этот файл PE является машинного кода.|  
|pe32BitPreferred|Указывает, что этот файл PE независимый от платформы и должен быть загружен в 32-разрядной среде, является предпочтительным.|  
  
## <a name="remarks"></a>Примечания  
 Эти значения можно использовать в побитовые сочетания.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
