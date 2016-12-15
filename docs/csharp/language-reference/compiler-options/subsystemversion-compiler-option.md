---
title: "-subsystemversion (параметры компилятора C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /subsystemversion (параметры компилятора C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает минимальную версию подсистемы, в которой может выполняться созданный исполняемый файл, то есть определяет версии Windows, в которых может работать исполняемый файл. Чаще всего этот параметр предоставляет исполняемому файлу возможность использовать определенные возможности безопасности, недоступные в прежних версиях Windows.  
  
> [!NOTE]
>  Чтобы задать саму подсистему, используйте [/target-](../../../csharp/language-reference/compiler-options/target-compiler-option.md) параметр компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
    -   [/ target: appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
  
    -   [/ target: winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
  
    -   [/platform:ARM](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)  
  
-   Значение по умолчанию — 6.00, если используется средство MSBuild, приложение предназначено для [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)], и не установлены параметры компилятора, определенные ранее в этом списке.  
  
-   Если ни одно из предыдущих условий не верно, значение по умолчанию — 4.00.  
  
## <a name="setting-this-option"></a>Задание этого параметра  
 Чтобы задать **/subsystemversion** параметра компилятора в Visual Studio, необходимо открыть CSPROJ-файл и указать значение для `SubsystemVersion` Свойства в MSBuild XML. Этот параметр невозможно задать в интегрированной среде разработки Visual Studio. Дополнительные сведения см. в разделе «Значения по умолчанию» ранее в этом разделе или [Общие свойства проектов MSBuild](/visual-studio/msbuild/common-msbuild-project-properties).  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)