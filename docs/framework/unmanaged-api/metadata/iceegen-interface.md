---
title: Интерфейс ICeeGen
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
ms.openlocfilehash: ae3c372951de00b097d0a8437039a3a85bf3aabf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426147"
---
# <a name="iceegen-interface"></a>Интерфейс ICeeGen
Предоставляет методы для динамической компиляции кода.  
  
 This interface is obsolete and should not be used.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Является устаревшей. Adds a .reloc instruction to the code base.|  
|[Метод AllocateMethodBuffer](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Является устаревшей. Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.|  
|[Метод ComputePointer](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Является устаревшей. Determines the buffer for the specified code section.|  
|[Метод EmitString](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Является устаревшей. Emits the specified string into the code base.|  
|[Метод GenerateCeeFile](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Является устаревшей. Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.|  
|[Метод GenerateCeeMemoryImage](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Является устаревшей. Generates an image in memory for the code base.|  
|[Метод GetIlSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Является устаревшей. Gets the section of the intermediate language code base referenced by the specified handle.|  
|[Метод GetIMapTokenIface](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Является устаревшей. Gets the interface referenced by the specified token.|  
|[Метод GetMethodBuffer](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Является устаревшей. Gets a buffer of the appropriate size for the method at the specified relative virtual address.|  
|[Метод GetSectionBlock](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Является устаревшей. Gets a section block of the code base.|  
|[Метод GetSectionCreate](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Является устаревшей. Generates and gets a code section using the specified name and flag values.|  
|[Метод GetSectionDataLen](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Является устаревшей. Gets the length of the specified section.|  
|[Метод GetString](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Является устаревшей. Gets the string stored at the specified relative virtual address.|  
|[Метод GetStringSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Является устаревшей. Gets a string representation of the code section referenced by the specified handle.|  
|[Метод TruncateSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Является устаревшей. Truncates the specified code section by the specified length.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Library:** Used as a resource in MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
