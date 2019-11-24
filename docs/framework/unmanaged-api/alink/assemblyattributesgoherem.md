---
title: AssemblyAttributesGoHereM Class (System.Runtime.CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereM
helpviewer_keywords:
- AssemblyAttributesGoHereM type
- Alink API, AssemblyAttributesGoHereM type
ms.assetid: caaa8ba9-b4bb-4dd6-934d-57e436b2f3e5
topic_type:
- apiref
ms.openlocfilehash: 15b9445aa3eabbd14541cfe5481bfb553c8c0347
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446635"
---
# <a name="assemblyattributesgoherem-class"></a>AssemblyAttributesGoHereM Class

Используется ALink как заполнитель для хранения сведений о пользовательских атрибутах.

## <a name="syntax"></a>Синтаксис

```csharp
internal sealed class AssemblyAttributesGoHereM
```

## <a name="remarks"></a>Заметки

Ссылки на этот тип можно включать в модули NETMODULE, источник которых содержат пользовательские атрибуты сборки. При построении манифеста сборки из одного или нескольких файлов, содержащих ссылки на эти NETMODULE, ALink использует сведения, подключенные к этим ссылкам, для выдачи фактических пользовательских атрибутов. Таким образом, экземпляр этого типа никогда не создается, а ссылки на него используются только как часть процесса сборки и бесполезны в окончательной сборке.

Ссылки на этот тип указывают пользовательские атрибуты, не связанные с безопасностью, но многократного использования.

These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.

## <a name="requirements"></a>Требования

mscorlib.dll

## <a name="see-also"></a>См. также

- [AssemblyAttributesGoHere](assemblyattributesgohere.md)
- [AssemblyAttributesGoHereS](assemblyattributesgoheres.md)
- [AssemblyAttributesGoHereSM](assemblyattributesgoheresm.md)
