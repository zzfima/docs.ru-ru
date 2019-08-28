---
title: Практическое руководство. Публикация метаданных для службы с использованием кода
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 51407e6d-4d87-42d5-be7c-9887b8652006
ms.openlocfilehash: 1faed5717c65c4973c3f1965df649df6f2e24722
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045897"
---
# <a name="how-to-publish-metadata-for-a-service-using-code"></a>Практическое руководство. Публикация метаданных для службы с использованием кода
Это один из двух инструкций, посвященных публикации метаданных для службы Windows Communication Foundation (WCF). Существуют два способа указать, как служба должна публиковать метаданные: с помощью файла конфигурации и с помощью кода. В этом разделе показано, как публиковать метаданные для службы с помощью кода.  
  
> [!CAUTION]
> В этом разделе показано, как опубликовать метаданные незащищенным образом. Любой клиент может получить метаданные из службы. Если требуется защита данных при публикации метаданных службой, см. раздел [Настраиваемая конечная точка безопасных метаданных](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).  
  
 Дополнительные сведения о публикации метаданных в файле конфигурации см. в разделе [как Публикация метаданных для службы с помощью файла](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)конфигурации. Публикация метаданных позволяет клиентам извлекать метаданные с помощью запроса WS-Transfer GET или запроса HTTP/GET, используя строку запроса `?wsdl`. Чтобы быть уверенным, что код работает, необходимо создать базовую службу WCF. Базовая резидентная служба представлена в следующем коде.  
  
 [!code-csharp[htPublishMetadataCode#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#0)]
 [!code-vb[htPublishMetadataCode#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#0)]  
  
### <a name="to-publish-metadata-in-code"></a>Публикация метаданных в коде  
  
1. В главном методе консольного приложения создайте экземпляр объекта <xref:System.ServiceModel.ServiceHost>, передав тип и базовый адрес службы.  
  
     [!code-csharp[htPublishMetadataCode#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#1)]
     [!code-vb[htPublishMetadataCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#1)]  
  
2. Создайте блок try сразу же после кода для шага 1, который перехватывает любые исключения, возникающие во время работы службы.  
  
     [!code-csharp[htPublishMetadataCode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#2)]
     [!code-vb[htPublishMetadataCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#2)]  
  
     [!code-csharp[htPublishMetadataCode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#3)]
     [!code-vb[htPublishMetadataCode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#3)]  
  
3. Проверьте, не содержит ли ведущее приложение службы <xref:System.ServiceModel.Description.ServiceMetadataBehavior>; если не содержит, создайте новый экземпляр <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
     [!code-csharp[htPublishMetadataCode#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#4)]
     [!code-vb[htPublishMetadataCode#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#4)]  
  
4. Задайте свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> значение `true.`  
  
     [!code-csharp[htPublishMetadataCode#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#5)]
     [!code-vb[htPublishMetadataCode#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#5)]  
  
5. <xref:System.ServiceModel.Description.ServiceMetadataBehavior> содержит свойство <xref:System.ServiceModel.Description.MetadataExporter>. <xref:System.ServiceModel.Description.MetadataExporter> содержит свойство <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>. Задайте для свойства <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> значение <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>. Свойству <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> можно также присвоить значение <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>. Если задано <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> средство экспорта метаданных, создает сведения о политике с метаданными, которые соответствует WS-Policy 1,5. Если задано значение <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>, модуль экспорта метаданных генерирует информацию о политике, соответствующую спецификации WS-Policy 1.2.  
  
     [!code-csharp[htPublishMetadataCode#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#6)]
     [!code-vb[htPublishMetadataCode#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#6)]  
  
6. Добавьте экземпляр <xref:System.ServiceModel.Description.ServiceMetadataBehavior> в коллекцию поведений ведущего приложения службы.  
  
     [!code-csharp[htPublishMetadataCode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#7)]
     [!code-vb[htPublishMetadataCode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#7)]  
  
7. Добавьте конечную точку обмена метаданными в ведущее приложение службы.  
  
     [!code-csharp[htPublishMetadataCode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#8)]
     [!code-vb[htPublishMetadataCode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#8)]  
  
8. Добавьте конечную точку приложения в ведущее приложение службы.  
  
     [!code-csharp[htPublishMetadataCode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#9)]
     [!code-vb[htPublishMetadataCode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#9)]  
  
    > [!NOTE]
    > Если в службу не добавлена ни одна конечная точка, то среда выполнения добавляет конечные точки по умолчанию. В этом примере, поскольку параметр <xref:System.ServiceModel.Description.ServiceMetadataBehavior> установлен в значение `true`, для службы включена публикация метаданных. Дополнительные сведения о конечных точках по умолчанию см. в разделе [упрощенная конфигурация](../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
9. Откройте ведущее приложение службы и ожидайте входящие сообщения. Когда пользователь нажмет клавишу ВВОД, закройте ведущее приложение службы.  
  
     [!code-csharp[htPublishMetadataCode#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#10)]
     [!code-vb[htPublishMetadataCode#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#10)]  
  
10. Постройте и запустите консольное приложение.  
  
11. С помощью Internet Explorer перейдите к базовому адресу службы (http://localhost:8001/MetadataSample в этом примере) и убедитесь, что публикация метаданных включена. Вверху веб-страницы должен отображаться заголовок «Простая служба», а сразу под ним - текст «Вы создали службу». Если нет, появится сообщение в верхней части полученной страницы: "Публикация метаданных для этой службы сейчас отключена".  
  
## <a name="example"></a>Пример  
 В следующем примере кода показана реализация базовой службы WCF, которая публикует метаданные для службы в коде.  
  
 [!code-csharp[htPublishMetadataCode#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#11)]
 [!code-vb[htPublishMetadataCode#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#11)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Размещение службы WCF в управляемом приложении](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
- [Резидентное размещение](../../../../docs/framework/wcf/samples/self-host.md)
- [Общие сведения об архитектуре метаданных](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)
- [Использование метаданных](../../../../docs/framework/wcf/feature-details/using-metadata.md)
- [Практическое руководство. Публикация метаданных для службы с помощью файла конфигурации](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
