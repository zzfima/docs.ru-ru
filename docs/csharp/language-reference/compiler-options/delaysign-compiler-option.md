---
title: -delaysign (параметры компилятора C#)
ms.date: 05/15/2018
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
ms.openlocfilehash: 9fdc02c22d9d8c8a709155e43a17ebf0d86dfd69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970445"
---
# <a name="-delaysign-c-compiler-options"></a>-delaysign (параметры компилятора C#)

Этот параметр указывает компилятору зарезервировать пространство в выходном файле, чтобы впоследствии добавить в него цифровую подпись.

## <a name="syntax"></a>Синтаксис

```console
-delaysign[ + | - ]
```

## <a name="arguments"></a>Аргументы

`+` &#124; `-`

Если требуется полностью подписанная сборка, используйте параметр **-delaysign-** . Если нужно лишь поместить в сборку открытый ключ, используйте параметр **-delaysign+** . Значение по умолчанию — **-delaysign-** .

## <a name="remarks"></a>Remarks

Параметр **-delaysign** никак не действует, если не использовать его с [-keyfile](./keyfile-compiler-option.md) или [-keycontainer](./keycontainer-compiler-option.md).

Параметры **-delaysign** и **-publicsign** — взаимоисключающие.

При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом. Эта операция предназначена для создания итоговой цифровой подписи, которая хранится в файле, содержащем манифест. При использовании отложенной подписи компилятор не вычисляет и не сохраняет подпись, а резервирует место в файле для добавления подписи в сборку в будущем.

Например, чтобы поместить сборку в глобальный кэш для тестирования, используйте параметр **-delaysign+** . После тестирования можно полностью подписать сборку, поместив в нее закрытый ключ с помощью [компоновщика сборок](../../../framework/tools/al-exe-assembly-linker.md).

Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](../../../standard/assembly/create-use-strong-named.md) и [Отложенная подпись сборки](../../../standard/assembly/delay-sign.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте страницу **свойств** для проекта.
1. Измените свойство **Только отложенная подпись**.

Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.

## <a name="see-also"></a>См. также раздел

- [Параметр -publicsign в C#](publicsign-compiler-option.md)
- [Параметры компилятора C# ](index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
