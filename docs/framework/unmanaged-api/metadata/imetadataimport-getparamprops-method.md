---
title: Метод IMetaDataImport::GetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05ac8efed8c0a905d2cfad433348a99fe578eeae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153183"
---
# <a name="imetadataimportgetparamprops-method"></a>Метод IMetaDataImport::GetParamProps
Возвращает значения метаданных для параметра, на который ссылается указанный токен ParamDef.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tk`  
 [in] Токен ParamDef, который представляет метаданные для возвращаемого параметра.  
  
 `pmd`  
 [out] Указатель на токен MethodDef, предоставляющий метод, который принимает параметр.  
  
 `pulSequence`  
 [out] Порядковая позиция параметра в списке аргументов метода.  
  
 `szName`  
 [out] Буфер для хранения имени параметра.  
  
 `cchName`  
 [in] Запрошенный размер в расширенных символах `szName`.  
  
 `pchName`  
 [out] Возвращаемый размер в расширенных символах `szName`.  
  
 `pdwAttr`  
 [out] Указатель на любой атрибут флаги, связанные с параметром. Это битовая маска `CorParamAttr` значения.  
  
 `pdwCPlusTypeFlag`  
 [out] Указатель на значение типа, указывающее флаг, параметр <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Указатель на строковую константу, возвращаемых параметром.  
  
 `pcchValue`  
 [out] Размер `ppValue` в расширенные символы, или нуль, если `ppValue` не содержит строку.  
  
## <a name="remarks"></a>Примечания

Последовательность значений элементов в `pulSequence` начинаются с 1 для параметров. Возвращаемое значение имеет порядковый номер 0.

## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
