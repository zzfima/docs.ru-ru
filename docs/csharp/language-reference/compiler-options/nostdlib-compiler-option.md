---
title: -nostdlib (параметры компилятора C#)
ms.date: 12/20/2019
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: ad8a2b5fc87dd7beee86d96331cf3961315be533
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345081"
---
# <a name="-nostdlib-c-compiler-options"></a>-nostdlib (параметры компилятора C#)

Параметр **-nostdlib** запрещает импорт библиотеки mscorlib.dll, которая определяет все пространство имен System.

## <a name="syntax"></a>Синтаксис

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a>Примечания

Используйте этот параметр, если вы хотите определить или создать собственное пространство имен System и объекты.

Если вы не укажете параметр **-nostdlib**, библиотека mscorlib.dll будет импортирована в вашу программу (как и при указании **-nostdlib-** ). Указание **-nostdlib** дает тот же результат, что и указание **-nostdlib+** .

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Установка параметра компилятора в Visual Studio

> [!NOTE]
> Следующие инструкции применимы только к Visual Studio 2015 (и более ранних версий). Свойство сборки **Не ссылаться на mscorlib.dll** отсутствует в более поздних версиях Visual Studio.

1. Откройте страницу **свойств** для проекта.

2. Щелкните страницу свойств **сборки** .

3. Нажмите кнопку **Дополнительно** .

4. Измените свойство **Не ссылаться на mscorlib.dll** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.

## <a name="see-also"></a>См. также

- [Параметры компилятора C# ](./index.md)
