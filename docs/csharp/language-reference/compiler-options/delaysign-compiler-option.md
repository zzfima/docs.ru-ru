---
title: "-delaysign (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /delaysign
dev_langs:
- CSharp
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ce4c9fbb14081764985f3b02988dff9ee272c451
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="delaysign-c-compiler-options"></a>/delaysign (параметры компилятора C#)
Этот параметр указывает компилятору зарезервировать пространство в выходном файле, чтобы впоследствии добавить в него цифровую подпись.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/delaysign[ + | - ]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Если требуется полностью подписанная сборка, используйте **/delaysign-**. Если необходимо только поместить в сборку открытый ключ, используйте параметр **/delaysign+**. Значение по умолчанию — **/delaysign-**.  
  
## <a name="remarks"></a>Примечания  
 Параметр **/delaysign** не оказывает никакого влияния, за исключением применения с [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) или [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).  
  
 При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом. Итоговая цифровая подпись хранится в файле, содержащем манифест. При использовании отложенной подписи компилятор не вычисляет и не сохраняет подпись, а резервирует место в файле для добавления подписи в сборку в будущем.  
  
 Например, чтобы поместить сборку в глобальный кэш для тестирования, используйте параметр **/delaysign+**. После тестирования можно полностью подписать сборку, поместив в нее закрытый ключ с помощью [компоновщика сборок](https://msdn.microsoft.com/library/c405shex).  
  
 Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](https://msdn.microsoft.com/library/xwb8f617) и [Отложенная подпись сборки](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **свойств** для проекта.  
  
2.  Измените свойство **Только отложенная подпись**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)

