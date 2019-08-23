---
title: Создание поставщика модели автоматизации пользовательского интерфейса на стороне клиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
ms.openlocfilehash: f9f7258c272ada867b406c5615c5d2d52e1d98a6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937915"
---
# <a name="create-a-client-side-ui-automation-provider"></a>Создание поставщика модели автоматизации пользовательского интерфейса на стороне клиента
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.  
  
 В этом разделе содержится пример кода, демонстрирующий реализацию клиентского поставщика автоматизации пользовательского интерфейса.  
  
## <a name="example"></a>Пример  
 Приведенный ниже пример кода можно встроить в библиотеку динамической компоновки (DLL), которая реализует очень простой поставщик на стороне клиента для окна консоли. Код не имеет никаких полезных функциональных возможностей, он предназначен для демонстрации основных действий по настройке сборки поставщика, которая может быть зарегистрирована клиентским приложением модели автоматизации пользовательского интерфейса.  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о поставщиках автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [Регистрация сборки поставщика на стороне клиента](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
