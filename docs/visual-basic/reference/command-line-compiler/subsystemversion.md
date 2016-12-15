---
title: "-subsystemversion (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "/subsystemversion - параметр компилятора [Visual Basic]"
  - "-subsystemversion - параметр компилятора [Visual Basic]"
  - "subsystemversion - параметр компилятора [Visual Basic]"
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /subsystemversion (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает минимальную версию подсистемы, в которой может выполняться созданный исполняемый файл, то есть определяет версии Windows, в которых может работать исполняемый файл. Чаще всего этот параметр предоставляет исполняемому файлу возможность использовать определенные возможности безопасности, недоступные в прежних версиях Windows.  
  
> [!NOTE]
>  Чтобы задать саму подсистему, используйте [/target-](../../../csharp/language-reference/compiler-options/target-compiler-option.md) параметр компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
/subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a>Параметры  
 `major.minor`  
 Минимальная требуемая версия подсистемы, через точку записывается основная и дополнительная версии. Например, можно указать, что приложение не может выполняться в операционной системе старше Windows 7, если задать для этого параметра значение 6.01, как указано в таблице ниже в этом разделе. Необходимо указать значения для параметра `major` и `minor` в виде целых чисел.  
  
 Нули в начале версии `minor` не изменяют версию, нули в конце — изменяют. Например, 6.1 и 6.01 — одна версия, а 6.10 — другая. Рекомендуется указывать дополнительный номер версии двумя цифрами, чтобы избежать путаницы.  
  
## <a name="remarks"></a>Примечания  
 В следующей таблице перечислены распространенные версии подсистем Windows.  
  
|Версия Windows|Версия подсистемы|  
|---------------------|-----------------------|  
|Windows 2000|5.00|  
|Windows XP|5.01|  
|Windows Server 2003|5.02|  
|Windows Vista|6.00|  
|Windows 7|6.01|  
|Windows Server 2008|6.01|  
|[!INCLUDE[win8](../../../csharp/language-reference/compiler-options/includes/win8_md.md)]|6.02|  
  
## <a name="default-values"></a>Значения по умолчанию  
 Значение по умолчанию **/subsystemversion** параметр компилятора зависит от условий в следующем списке:  
  
-   Значение по умолчанию — 6.02, если задан любой параметр компилятора из следующего списка.  
  
    -   [/ target: appcontainerexe](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [/ target: winmdobj](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [/platform:ARM](../../../visual-basic/reference/command-line-compiler/platform.md)  
  
-   Значение по умолчанию — 6.00, если используется средство MSBuild, приложение предназначено для [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)], и не установлены параметры компилятора, определенные ранее в этом списке.  
  
-   Если ни одно из предыдущих условий не верно, значение по умолчанию — 4.00.  
  
## <a name="setting-this-option"></a>Задание этого параметра  
 Чтобы задать **/subsystemversion** параметра компилятора в Visual Studio, необходимо открыть VBPROJ-файл и указать значение для `SubsystemVersion` Свойства в MSBuild XML. Этот параметр невозможно задать в интегрированной среде разработки Visual Studio. Дополнительные сведения см. в разделе «Значения по умолчанию» ранее в этом разделе или [Общие свойства проектов MSBuild](/visual-studio/msbuild/common-msbuild-project-properties).  
  

  
## <a name="see-also"></a>См. также раздел  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
 [свойства MSBuild](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/ee3538c5-0d7d-4c18-a1d7-edf460cd1c8a/locales/en-US)