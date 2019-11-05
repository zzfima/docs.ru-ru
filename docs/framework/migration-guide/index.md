---
title: 'Руководство по переходу на .NET Framework 4.8, 4.7, 4.6 и 4.5 '
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
ms.openlocfilehash: 350d5400b4e1df7238702ce925c974eecb2a0d7a
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457950"
---
# <a name="migration-guide-to-the-net-framework-48-47-46-and-45"></a>Руководство по переходу на .NET Framework 4.8, 4.7, 4.6 и 4.5

Если приложение создано с использованием более ранней версии .NET Framework, обычно его можно легко обновить до версии .NET Framework 4.5 и ее доработанных выпусков (4.5.1 и 4.5.2), версии NET Framework 4.6 и ее доработанных выпусков (4.6.1 и 4.6.2), версии .NET Framework 4.7 и ее доработанных выпусков (4.7.1 и 4.7.2) или версии .NET Framework 4.8. Откройте проект в Visual Studio. Если проект был создан в более ранней версии Visual Studio, автоматически откроется диалоговое окно **Совместимость проекта**. Дополнительные сведения об обновлении проекта в Visual Studio см. в статьях [о переносе, миграции и обновлении проектов Visual Studio](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) и [целевой платформе и совместимости для Visual Studio 2019](/visualstudio/releases/2019/compatibility).

 Однако некоторые изменения в платформе .NET Framework требуют внесения изменений в код. Кроме того, возможно, вы захотите воспользоваться преимуществами новых возможностей в версии .NET Framework 4.5 и ее доработанных выпусках, в версии .NET Framework 4.6 и ее доработанных выпусках, в версии .NET Framework 4.7 и ее доработанных выпусках или в версии .NET Framework 4.8. Внесение подобных изменений в приложение для новой версии платформы .NET Framework обычно называется *миграцией*. Если нет необходимости в миграции приложения, его можно выполнить в среде .NET Framework 4.5 и более поздней версии без компиляции.

## <a name="migration-resources"></a>Ресурсы миграции

Перед миграцией приложения из более ранних версий .NET Framework в версию 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 или 4.8 просмотрите следующие документы:

- См. раздел [Версии и зависимости](versions-and-dependencies.md), чтобы определить версию среды CLR, лежащую в основе каждой версии .NET Framework, и ознакомиться с рекомендациями по определению целевой платформы для приложений.

- См. сведения о [совместимости приложений](application-compatibility.md), чтобы узнать об изменениях среды выполнения и целевой платформы, которые могут повлиять на приложение, а также о том, что с ними делать.

- Просмотрите раздел [Устаревшие классы библиотеки классов](../whats-new/whats-obsolete.md), чтобы определить устаревшие типы и члены в коде и рекомендуемые альтернативы.

- См. раздел [Новые возможности](../whats-new/index.md), чтобы узнать о новых возможностях, которые вы, возможно, захотите добавить в приложение.

## <a name="see-also"></a>См. также

- [Совместимость приложений](application-compatibility.md)
- [Миграция из .NET Framework 1.1](migrating-from-the-net-framework-1-1.md)
- [Совместимость версий](version-compatibility.md)
- [Версии и зависимости](versions-and-dependencies.md)
- [Практическое руководство. Настройка приложения для включения поддержки .NET Framework версии 4 и выше](how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Новые возможности](../whats-new/index.md)
- [Устаревшие классы библиотеки классов](../whats-new/whats-obsolete.md)
- [Сведения о версиях и сборках платформы .NET Framework](https://go.microsoft.com/fwlink/?LinkId=201701)
- [Политика жизненного цикла поддержки Microsoft .NET Framework](https://go.microsoft.com/fwlink/?LinkId=196607)
- [Проблемы при миграции на .NET Framework 4](net-framework-4-migration-issues.md)
