---
title: Алгоритм загрузки неуправляемых библиотек (.NET Core)
description: Подробные сведения об алгоритме загрузки неуправляемых сборок в .NET Core
ms.date: 10/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: c651aa6e0f37a968e6f8b26d1909def6fa488ccd
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2019
ms.locfileid: "72303698"
---
# <a name="unmanaged-native-library-loading-algorithm"></a>Алгоритм загрузки неуправляемых (собственных) библиотек

Неуправляемые библиотеки обнаруживаются и загружаются по специальному алгоритму, который состоит из нескольких этапов.

Следующий алгоритм описывает, как загружаются собственные сборки через `PInvoke`.

## <a name="pinvoke-load-library-algorithm"></a>Алгоритм `PInvoke` для загрузки библиотек

`PInvoke` использует следующий алгоритм при попытке загрузить неуправляемую сборку.

1. Определяется `active` <xref:System.Runtime.Loader.AssemblyLoadContext>. Для неуправляемой библиотеки `active` AssemblyLoadContext получает значение, соответствующее сборке, которая определяет `PInvoke`.

2. Для `active` <xref:System.Runtime.Loader.AssemblyLoadContext> выполняется попытка найти сборку в следующем порядке приоритета:
    * Проверяется кэш.

    * Вызывается текущий делегат <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType>, заданный функцией <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType>.

    * Вызывается функция <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> в `active` AssemblyLoadContext.

    * Проверяется кэш экземпляров <xref:System.AppDomain> и выполняется логика [зондирования неуправляемой (собственной) библиотеки](default-probing.md#unmanaged-native-library-probing).

    * Вызывается событие <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> для `active` AssemblyLoadContext.
