---
title: -delaysign (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
ms.openlocfilehash: f8525a4e96d172709673b94316b06d815535805f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-delaysign-c-compiler-options"></a>-delaysign (параметры компилятора C#)
Этот параметр указывает компилятору зарезервировать пространство в выходном файле, чтобы впоследствии добавить в него цифровую подпись.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-delaysign[ + | - ]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Если требуется полностью подписанная сборка, используйте параметр **-delaysign-**. Если нужно лишь поместить в сборку открытый ключ, используйте параметр **-delaysign+**. Значение по умолчанию — **-delaysign-**.  
  
## <a name="remarks"></a>Примечания  
 Параметр **-delaysign** никак не действует, если не использовать его с [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) или [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).  
  
 При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом. Итоговая цифровая подпись хранится в файле, содержащем манифест. При использовании отложенной подписи компилятор не вычисляет и не сохраняет подпись, а резервирует место в файле для добавления подписи в сборку в будущем.  
  
 Например, чтобы поместить сборку в глобальный кэш для тестирования, используйте параметр **-delaysign+**. После тестирования можно полностью подписать сборку, поместив в нее закрытый ключ с помощью [компоновщика сборок](../../../framework/tools/al-exe-assembly-linker.md).  
  
 Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) и [Отложенная подпись сборки](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **свойств** для проекта.  
  
2.  Измените свойство **Только отложенная подпись**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
