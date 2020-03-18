---
title: -refonly (параметры компилятора C#)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: 856b65d3b2217dbe5d53ecda00723b47247d80a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72773856"
---
# <a name="-refonly-c-compiler-options"></a>-refonly (параметры компилятора C#)

Параметр **-refonly** указывает на то, что в качестве основных выходных данных должна быть выведена базовая сборка, а не сборка реализации. Параметр `-refonly` автоматически отключает вывод файлов PDB, так как базовые сборки не могут выполняться. Этот параметр соответствует свойству проекта [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) в MSBuild.

## <a name="syntax"></a>Синтаксис

```console
-refonly
```

## <a name="remarks"></a>Remarks

Базовые сборки являются особым типом сборки, которая содержит только минимальный объем метаданных, необходимый для представления общедоступного API-интерфейса библиотеки. Такие сборки включают в себя объявления для всех элементов, которые важны при указании ссылки на сборку в средствах сборки, но исключают все реализации элементов, а также объявления закрытых элементов, не имеющих наблюдаемого влияния на их контракт API. Дополнительные сведения см. в разделе [Базовые сборки](../../../standard/assembly/reference-assemblies.md) в руководстве по .NET.

Параметры `-refonly` и [`-refout`](refout-compiler-option.md) являются взаимоисключающими.

## <a name="see-also"></a>См. также раздел

- [Параметры компилятора C# ](./index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
