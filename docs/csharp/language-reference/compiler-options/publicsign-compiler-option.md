---
title: -publicsign (параметры компилятора C#)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: de7d9c98b0f279b52bc93711c5b986a2b2e57215
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738070"
---
# <a name="-publicsign-c-compiler-options"></a>-publicsign (параметры компилятора C#)

Этот параметр указывает компилятору на необходимость применения открытого ключа, но фактически не подписывает сборку. Кроме того, параметр **-publicsign** задает в сборке бит, который сообщает среде выполнения, что файл подписан.

## <a name="syntax"></a>Синтаксис

```console
-publicsign
```

## <a name="arguments"></a>Аргументы

Отсутствует.

## <a name="remarks"></a>Примечания

С параметром **-publicsign** необходимо использовать параметр [-keyfile](keyfile-compiler-option.md) или [-keycontainer](keycontainer-compiler-option.md). Каждый из параметров **keyfile** и **keycontainer** определяет открытый ключ.

Параметры **-publicsign** и **-delaysign** — взаимоисключающие.

При таком подписывании в сборку добавляется открытый ключ. Кроме того, в сборке устанавливается флаг "подписано", хотя фактически сборка не подписывается закрытым ключом. Такой подход иногда называют "фиктивным подписыванием" или "подписыванием OSS". Он полезен на проектах с открытым исходным кодом: людям нужно создавать сборки, которые будут совместимы с выпущенными "полностью подписанными" сборками, но у них нет доступа к закрытому ключу, который использовался для подписывания сборок. Так как потребителям практически никогда не нужно проверять, полностью ли подписана сборка, создаваемые сообществами сборки можно использовать практические во всех случаях, в которых может использоваться полностью подписанная сборка.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте страницу **свойств** для проекта.
1. Измените свойство **Только отложенная подпись**.

## <a name="see-also"></a>См. также

- [-delaysign (параметры компилятора C#)](delaysign-compiler-option.md)
- [-keyfile (параметры компилятора C#)](keyfile-compiler-option.md)
- [-keycontainer (параметры компилятора C#)](keycontainer-compiler-option.md)
- [Параметры компилятора C# ](index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
