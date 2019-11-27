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
  
 Этот интерфейс устарел и не должен использоваться.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Является устаревшей. Добавляет инструкцию. reloc в базу кода.|  
|[Метод AllocateMethodBuffer](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Является устаревшей. Создает буфер указанного размера для метода и получает относительный виртуальный адрес метода.|  
|[Метод ComputePointer](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Является устаревшей. Определяет буфер для указанного раздела кода.|  
|[Метод EmitString](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Является устаревшей. Порождает указанную строку в базу кода.|  
|[Метод GenerateCeeFile](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Является устаревшей. Создает файл с базовым кодом, который содержит базу кода, загруженную в данный момент в этот `ICeeGen`.|  
|[Метод GenerateCeeMemoryImage](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Является устаревшей. Создает изображение в памяти для базы кода.|  
|[Метод GetIlSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Является устаревшей. Возвращает раздел базы кода промежуточного языка, на который ссылается указанный обработчик.|  
|[Метод GetIMapTokenIface](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Является устаревшей. Возвращает интерфейс, на который ссылается указанный токен.|  
|[Метод GetMethodBuffer](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Является устаревшей. Возвращает буфер соответствующего размера для метода по указанному относительному виртуальному адресу.|  
|[Метод GetSectionBlock](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Является устаревшей. Возвращает блок базы кода.|  
|[Метод GetSectionCreate](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Является устаревшей. Создает и получает раздел кода, используя указанные значения имени и флага.|  
|[Метод GetSectionDataLen](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Является устаревшей. Возвращает длину указанного раздела.|  
|[Метод GetString](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Является устаревшей. Возвращает строку, хранящуюся по указанному относительному виртуальному адресу.|  
|[Метод GetStringSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Является устаревшей. Возвращает строковое представление раздела кода, на который ссылается указанный маркер.|  
|[Метод TruncateSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Является устаревшей. Усекает указанный раздел кода на заданную длину.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
