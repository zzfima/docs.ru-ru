---
title: Коллекции схемы OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164688"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="21069-102">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="21069-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="21069-103">В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="21069-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="21069-104">Поставщик OLE DB для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="21069-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="21069-105">Драйвер Microsoft SQL Server OLE DB поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="21069-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="21069-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="21069-106">Tables</span></span>  
  
-   <span data-ttu-id="21069-107">Столбцы</span><span class="sxs-lookup"><span data-stu-id="21069-107">Columns</span></span>  
  
-   <span data-ttu-id="21069-108">Процедуры</span><span class="sxs-lookup"><span data-stu-id="21069-108">Procedures</span></span>  
  
-   <span data-ttu-id="21069-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="21069-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="21069-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="21069-110">Catalog</span></span>  
  
-   <span data-ttu-id="21069-111">Индексы</span><span class="sxs-lookup"><span data-stu-id="21069-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="21069-112">Таблицы</span><span class="sxs-lookup"><span data-stu-id="21069-112">Tables</span></span>  
  
|<span data-ttu-id="21069-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-113">ColumnName</span></span>|<span data-ttu-id="21069-114">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-115">TABLE_CATALOG</span></span>|<span data-ttu-id="21069-116">String</span><span class="sxs-lookup"><span data-stu-id="21069-116">String</span></span>|  
|<span data-ttu-id="21069-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="21069-118">String</span><span class="sxs-lookup"><span data-stu-id="21069-118">String</span></span>|  
|<span data-ttu-id="21069-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-119">TABLE_NAME</span></span>|<span data-ttu-id="21069-120">String</span><span class="sxs-lookup"><span data-stu-id="21069-120">String</span></span>|  
|<span data-ttu-id="21069-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-121">TABLE_TYPE</span></span>|<span data-ttu-id="21069-122">String</span><span class="sxs-lookup"><span data-stu-id="21069-122">String</span></span>|  
|<span data-ttu-id="21069-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-123">TABLE_GUID</span></span>|<span data-ttu-id="21069-124">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-124">Guid</span></span>|  
|<span data-ttu-id="21069-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-125">DESCRIPTION</span></span>|<span data-ttu-id="21069-126">String</span><span class="sxs-lookup"><span data-stu-id="21069-126">String</span></span>|  
|<span data-ttu-id="21069-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="21069-127">TABLE_PROPID</span></span>|<span data-ttu-id="21069-128">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-128">Int64</span></span>|  
|<span data-ttu-id="21069-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="21069-129">DATE_CREATED</span></span>|<span data-ttu-id="21069-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-130">DateTime</span></span>|  
|<span data-ttu-id="21069-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="21069-131">DATE_MODIFIED</span></span>|<span data-ttu-id="21069-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="21069-133">Столбцы</span><span class="sxs-lookup"><span data-stu-id="21069-133">Columns</span></span>  
  
|<span data-ttu-id="21069-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-134">ColumnName</span></span>|<span data-ttu-id="21069-135">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-136">TABLE_CATALOG</span></span>|<span data-ttu-id="21069-137">String</span><span class="sxs-lookup"><span data-stu-id="21069-137">String</span></span>|  
|<span data-ttu-id="21069-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="21069-139">String</span><span class="sxs-lookup"><span data-stu-id="21069-139">String</span></span>|  
|<span data-ttu-id="21069-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-140">TABLE_NAME</span></span>|<span data-ttu-id="21069-141">String</span><span class="sxs-lookup"><span data-stu-id="21069-141">String</span></span>|  
|<span data-ttu-id="21069-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-142">COLUMN_NAME</span></span>|<span data-ttu-id="21069-143">String</span><span class="sxs-lookup"><span data-stu-id="21069-143">String</span></span>|  
|<span data-ttu-id="21069-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-144">COLUMN_GUID</span></span>|<span data-ttu-id="21069-145">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-145">Guid</span></span>|  
|<span data-ttu-id="21069-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="21069-146">COLUMN_PROPID</span></span>|<span data-ttu-id="21069-147">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-147">Int64</span></span>|  
|<span data-ttu-id="21069-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="21069-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="21069-149">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-149">Int64</span></span>|  
|<span data-ttu-id="21069-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="21069-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="21069-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-151">Boolean</span></span>|  
|<span data-ttu-id="21069-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="21069-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="21069-153">String</span><span class="sxs-lookup"><span data-stu-id="21069-153">String</span></span>|  
|<span data-ttu-id="21069-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="21069-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="21069-155">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-155">Int64</span></span>|  
|<span data-ttu-id="21069-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="21069-156">IS_NULLABLE</span></span>|<span data-ttu-id="21069-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-157">Boolean</span></span>|  
|<span data-ttu-id="21069-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-158">DATA_TYPE</span></span>|<span data-ttu-id="21069-159">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-159">Int32</span></span>|  
|<span data-ttu-id="21069-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-160">TYPE_GUID</span></span>|<span data-ttu-id="21069-161">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-161">Guid</span></span>|  
|<span data-ttu-id="21069-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="21069-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="21069-163">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-163">Int64</span></span>|  
|<span data-ttu-id="21069-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="21069-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="21069-165">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-165">Int64</span></span>|  
|<span data-ttu-id="21069-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="21069-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="21069-167">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-167">Int32</span></span>|  
|<span data-ttu-id="21069-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="21069-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="21069-169">Int16</span><span class="sxs-lookup"><span data-stu-id="21069-169">Int16</span></span>|  
|<span data-ttu-id="21069-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="21069-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="21069-171">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-171">Int64</span></span>|  
|<span data-ttu-id="21069-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="21069-173">String</span><span class="sxs-lookup"><span data-stu-id="21069-173">String</span></span>|  
|<span data-ttu-id="21069-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="21069-175">String</span><span class="sxs-lookup"><span data-stu-id="21069-175">String</span></span>|  
|<span data-ttu-id="21069-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="21069-177">String</span><span class="sxs-lookup"><span data-stu-id="21069-177">String</span></span>|  
|<span data-ttu-id="21069-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="21069-179">String</span><span class="sxs-lookup"><span data-stu-id="21069-179">String</span></span>|  
|<span data-ttu-id="21069-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="21069-181">String</span><span class="sxs-lookup"><span data-stu-id="21069-181">String</span></span>|  
|<span data-ttu-id="21069-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-182">COLLATION_NAME</span></span>|<span data-ttu-id="21069-183">String</span><span class="sxs-lookup"><span data-stu-id="21069-183">String</span></span>|  
|<span data-ttu-id="21069-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="21069-185">String</span><span class="sxs-lookup"><span data-stu-id="21069-185">String</span></span>|  
|<span data-ttu-id="21069-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="21069-187">String</span><span class="sxs-lookup"><span data-stu-id="21069-187">String</span></span>|  
|<span data-ttu-id="21069-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-188">DOMAIN_NAME</span></span>|<span data-ttu-id="21069-189">String</span><span class="sxs-lookup"><span data-stu-id="21069-189">String</span></span>|  
|<span data-ttu-id="21069-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-190">DESCRIPTION</span></span>|<span data-ttu-id="21069-191">String</span><span class="sxs-lookup"><span data-stu-id="21069-191">String</span></span>|  
|<span data-ttu-id="21069-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="21069-192">COLUMN_LCID</span></span>|<span data-ttu-id="21069-193">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-193">Int32</span></span>|  
|<span data-ttu-id="21069-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="21069-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="21069-195">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-195">Int32</span></span>|  
|<span data-ttu-id="21069-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="21069-196">COLUMN_SORTID</span></span>|<span data-ttu-id="21069-197">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-197">Int32</span></span>|  
|<span data-ttu-id="21069-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="21069-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="21069-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="21069-199">Byte[]</span></span>|  
|<span data-ttu-id="21069-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="21069-200">IS_COMPUTED</span></span>|<span data-ttu-id="21069-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="21069-202">Процедуры</span><span class="sxs-lookup"><span data-stu-id="21069-202">Procedures</span></span>  
  
|<span data-ttu-id="21069-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-203">ColumnName</span></span>|<span data-ttu-id="21069-204">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="21069-206">String</span><span class="sxs-lookup"><span data-stu-id="21069-206">String</span></span>|  
|<span data-ttu-id="21069-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="21069-208">String</span><span class="sxs-lookup"><span data-stu-id="21069-208">String</span></span>|  
|<span data-ttu-id="21069-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="21069-210">String</span><span class="sxs-lookup"><span data-stu-id="21069-210">String</span></span>|  
|<span data-ttu-id="21069-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="21069-212">Int16</span><span class="sxs-lookup"><span data-stu-id="21069-212">Int16</span></span>|  
|<span data-ttu-id="21069-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="21069-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="21069-214">String</span><span class="sxs-lookup"><span data-stu-id="21069-214">String</span></span>|  
|<span data-ttu-id="21069-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-215">DESCRIPTION</span></span>|<span data-ttu-id="21069-216">String</span><span class="sxs-lookup"><span data-stu-id="21069-216">String</span></span>|  
|<span data-ttu-id="21069-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="21069-217">DATE_CREATED</span></span>|<span data-ttu-id="21069-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-218">DateTime</span></span>|  
|<span data-ttu-id="21069-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="21069-219">DATE_MODIFIED</span></span>|<span data-ttu-id="21069-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="21069-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="21069-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="21069-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-222">ColumnName</span></span>|<span data-ttu-id="21069-223">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="21069-225">String</span><span class="sxs-lookup"><span data-stu-id="21069-225">String</span></span>|  
|<span data-ttu-id="21069-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="21069-227">String</span><span class="sxs-lookup"><span data-stu-id="21069-227">String</span></span>|  
|<span data-ttu-id="21069-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="21069-229">String</span><span class="sxs-lookup"><span data-stu-id="21069-229">String</span></span>|  
|<span data-ttu-id="21069-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-230">PARAMETER_NAME</span></span>|<span data-ttu-id="21069-231">String</span><span class="sxs-lookup"><span data-stu-id="21069-231">String</span></span>|  
|<span data-ttu-id="21069-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="21069-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="21069-233">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-233">Int32</span></span>|  
|<span data-ttu-id="21069-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="21069-235">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-235">Int32</span></span>|  
|<span data-ttu-id="21069-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="21069-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="21069-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-237">Boolean</span></span>|  
|<span data-ttu-id="21069-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="21069-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="21069-239">String</span><span class="sxs-lookup"><span data-stu-id="21069-239">String</span></span>|  
|<span data-ttu-id="21069-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="21069-240">IS_NULLABLE</span></span>|<span data-ttu-id="21069-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-241">Boolean</span></span>|  
|<span data-ttu-id="21069-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-242">DATA_TYPE</span></span>|<span data-ttu-id="21069-243">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-243">Int32</span></span>|  
|<span data-ttu-id="21069-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="21069-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="21069-245">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-245">Int64</span></span>|  
|<span data-ttu-id="21069-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="21069-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="21069-247">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-247">Int64</span></span>|  
|<span data-ttu-id="21069-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="21069-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="21069-249">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-249">Int32</span></span>|  
|<span data-ttu-id="21069-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="21069-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="21069-251">Int16</span><span class="sxs-lookup"><span data-stu-id="21069-251">Int16</span></span>|  
|<span data-ttu-id="21069-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-252">DESCRIPTION</span></span>|<span data-ttu-id="21069-253">String</span><span class="sxs-lookup"><span data-stu-id="21069-253">String</span></span>|  
|<span data-ttu-id="21069-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-254">TYPE_NAME</span></span>|<span data-ttu-id="21069-255">String</span><span class="sxs-lookup"><span data-stu-id="21069-255">String</span></span>|  
|<span data-ttu-id="21069-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="21069-257">String</span><span class="sxs-lookup"><span data-stu-id="21069-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="21069-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="21069-258">Catalog</span></span>  
  
|<span data-ttu-id="21069-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-259">ColumnName</span></span>|<span data-ttu-id="21069-260">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-261">CATALOG_NAME</span></span>|<span data-ttu-id="21069-262">String</span><span class="sxs-lookup"><span data-stu-id="21069-262">String</span></span>|  
|<span data-ttu-id="21069-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-263">DESCRIPTION</span></span>|<span data-ttu-id="21069-264">String</span><span class="sxs-lookup"><span data-stu-id="21069-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="21069-265">Индексы</span><span class="sxs-lookup"><span data-stu-id="21069-265">Indexes</span></span>  
  
|<span data-ttu-id="21069-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-266">ColumnName</span></span>|<span data-ttu-id="21069-267">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-268">TABLE_CATALOG</span></span>|<span data-ttu-id="21069-269">String</span><span class="sxs-lookup"><span data-stu-id="21069-269">String</span></span>|  
|<span data-ttu-id="21069-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="21069-271">String</span><span class="sxs-lookup"><span data-stu-id="21069-271">String</span></span>|  
|<span data-ttu-id="21069-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-272">TABLE_NAME</span></span>|<span data-ttu-id="21069-273">String</span><span class="sxs-lookup"><span data-stu-id="21069-273">String</span></span>|  
|<span data-ttu-id="21069-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-274">INDEX_CATALOG</span></span>|<span data-ttu-id="21069-275">String</span><span class="sxs-lookup"><span data-stu-id="21069-275">String</span></span>|  
|<span data-ttu-id="21069-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="21069-277">String</span><span class="sxs-lookup"><span data-stu-id="21069-277">String</span></span>|  
|<span data-ttu-id="21069-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-278">INDEX_NAME</span></span>|<span data-ttu-id="21069-279">String</span><span class="sxs-lookup"><span data-stu-id="21069-279">String</span></span>|  
|<span data-ttu-id="21069-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="21069-280">PRIMARY_KEY</span></span>|<span data-ttu-id="21069-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-281">Boolean</span></span>|  
|<span data-ttu-id="21069-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="21069-282">UNIQUE</span></span>|<span data-ttu-id="21069-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-283">Boolean</span></span>|  
|<span data-ttu-id="21069-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="21069-284">CLUSTERED</span></span>|<span data-ttu-id="21069-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-285">Boolean</span></span>|  
|<span data-ttu-id="21069-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-286">TYPE</span></span>|<span data-ttu-id="21069-287">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-287">Int32</span></span>|  
|<span data-ttu-id="21069-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="21069-288">FILL_FACTOR</span></span>|<span data-ttu-id="21069-289">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-289">Int32</span></span>|  
|<span data-ttu-id="21069-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="21069-290">INITIAL_SIZE</span></span>|<span data-ttu-id="21069-291">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-291">Int32</span></span>|  
|<span data-ttu-id="21069-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="21069-292">NULLS</span></span>|<span data-ttu-id="21069-293">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-293">Int32</span></span>|  
|<span data-ttu-id="21069-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="21069-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="21069-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-295">Boolean</span></span>|  
|<span data-ttu-id="21069-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="21069-296">AUTO_UPDATE</span></span>|<span data-ttu-id="21069-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-297">Boolean</span></span>|  
|<span data-ttu-id="21069-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="21069-298">NULL_COLLATION</span></span>|<span data-ttu-id="21069-299">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-299">Int32</span></span>|  
|<span data-ttu-id="21069-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="21069-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="21069-301">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-301">Int64</span></span>|  
|<span data-ttu-id="21069-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-302">COLUMN_NAME</span></span>|<span data-ttu-id="21069-303">String</span><span class="sxs-lookup"><span data-stu-id="21069-303">String</span></span>|  
|<span data-ttu-id="21069-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-304">COLUMN_GUID</span></span>|<span data-ttu-id="21069-305">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-305">Guid</span></span>|  
|<span data-ttu-id="21069-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="21069-306">COLUMN_PROPID</span></span>|<span data-ttu-id="21069-307">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-307">Int64</span></span>|  
|<span data-ttu-id="21069-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="21069-308">COLLATION</span></span>|<span data-ttu-id="21069-309">Int16</span><span class="sxs-lookup"><span data-stu-id="21069-309">Int16</span></span>|  
|<span data-ttu-id="21069-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="21069-310">CARDINALITY</span></span>|<span data-ttu-id="21069-311">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="21069-311">Decimal</span></span>|  
|<span data-ttu-id="21069-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="21069-312">PAGES</span></span>|<span data-ttu-id="21069-313">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-313">Int32</span></span>|  
|<span data-ttu-id="21069-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="21069-314">FILTER_CONDITION</span></span>|<span data-ttu-id="21069-315">String</span><span class="sxs-lookup"><span data-stu-id="21069-315">String</span></span>|  
|<span data-ttu-id="21069-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="21069-316">INTEGRATED</span></span>|<span data-ttu-id="21069-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="21069-318">Поставщик Microsoft OLE DB для Oracle</span><span class="sxs-lookup"><span data-stu-id="21069-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="21069-319">Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="21069-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="21069-320">Таблицы</span><span class="sxs-lookup"><span data-stu-id="21069-320">Tables</span></span>  
  
-   <span data-ttu-id="21069-321">Столбцы</span><span class="sxs-lookup"><span data-stu-id="21069-321">Columns</span></span>  
  
-   <span data-ttu-id="21069-322">Процедуры</span><span class="sxs-lookup"><span data-stu-id="21069-322">Procedures</span></span>  
  
-   <span data-ttu-id="21069-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="21069-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="21069-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="21069-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="21069-325">Представления</span><span class="sxs-lookup"><span data-stu-id="21069-325">Views</span></span>  
  
-   <span data-ttu-id="21069-326">Индексы</span><span class="sxs-lookup"><span data-stu-id="21069-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="21069-327">Таблицы</span><span class="sxs-lookup"><span data-stu-id="21069-327">Tables</span></span>  
  
|<span data-ttu-id="21069-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-328">ColumnName</span></span>|<span data-ttu-id="21069-329">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-330">TABLE_CATALOG</span></span>|<span data-ttu-id="21069-331">String</span><span class="sxs-lookup"><span data-stu-id="21069-331">String</span></span>|  
|<span data-ttu-id="21069-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="21069-333">String</span><span class="sxs-lookup"><span data-stu-id="21069-333">String</span></span>|  
|<span data-ttu-id="21069-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-334">TABLE_NAME</span></span>|<span data-ttu-id="21069-335">String</span><span class="sxs-lookup"><span data-stu-id="21069-335">String</span></span>|  
|<span data-ttu-id="21069-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-336">TABLE_TYPE</span></span>|<span data-ttu-id="21069-337">String</span><span class="sxs-lookup"><span data-stu-id="21069-337">String</span></span>|  
|<span data-ttu-id="21069-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-338">TABLE_GUID</span></span>|<span data-ttu-id="21069-339">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-339">Guid</span></span>|  
|<span data-ttu-id="21069-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-340">DESCRIPTION</span></span>|<span data-ttu-id="21069-341">String</span><span class="sxs-lookup"><span data-stu-id="21069-341">String</span></span>|  
|<span data-ttu-id="21069-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="21069-342">TABLE_PROPID</span></span>|<span data-ttu-id="21069-343">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-343">Int64</span></span>|  
|<span data-ttu-id="21069-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="21069-344">DATE_CREATED</span></span>|<span data-ttu-id="21069-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-345">DateTime</span></span>|  
|<span data-ttu-id="21069-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="21069-346">DATE_MODIFIED</span></span>|<span data-ttu-id="21069-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="21069-348">Столбцы</span><span class="sxs-lookup"><span data-stu-id="21069-348">Columns</span></span>  
  
|<span data-ttu-id="21069-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-349">ColumnName</span></span>|<span data-ttu-id="21069-350">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-351">TABLE_CATALOG</span></span>|<span data-ttu-id="21069-352">String</span><span class="sxs-lookup"><span data-stu-id="21069-352">String</span></span>|  
|<span data-ttu-id="21069-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="21069-354">String</span><span class="sxs-lookup"><span data-stu-id="21069-354">String</span></span>|  
|<span data-ttu-id="21069-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-355">TABLE_NAME</span></span>|<span data-ttu-id="21069-356">String</span><span class="sxs-lookup"><span data-stu-id="21069-356">String</span></span>|  
|<span data-ttu-id="21069-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-357">COLUMN_NAME</span></span>|<span data-ttu-id="21069-358">String</span><span class="sxs-lookup"><span data-stu-id="21069-358">String</span></span>|  
|<span data-ttu-id="21069-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-359">COLUMN_GUID</span></span>|<span data-ttu-id="21069-360">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-360">Guid</span></span>|  
|<span data-ttu-id="21069-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="21069-361">COLUMN_PROPID</span></span>|<span data-ttu-id="21069-362">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-362">Int64</span></span>|  
|<span data-ttu-id="21069-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="21069-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="21069-364">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-364">Int64</span></span>|  
|<span data-ttu-id="21069-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="21069-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="21069-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-366">Boolean</span></span>|  
|<span data-ttu-id="21069-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="21069-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="21069-368">String</span><span class="sxs-lookup"><span data-stu-id="21069-368">String</span></span>|  
|<span data-ttu-id="21069-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="21069-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="21069-370">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-370">Int64</span></span>|  
|<span data-ttu-id="21069-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="21069-371">IS_NULLABLE</span></span>|<span data-ttu-id="21069-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-372">Boolean</span></span>|  
|<span data-ttu-id="21069-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-373">DATA_TYPE</span></span>|<span data-ttu-id="21069-374">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-374">Int32</span></span>|  
|<span data-ttu-id="21069-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-375">TYPE_GUID</span></span>|<span data-ttu-id="21069-376">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-376">Guid</span></span>|  
|<span data-ttu-id="21069-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="21069-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="21069-378">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-378">Int64</span></span>|  
|<span data-ttu-id="21069-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="21069-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="21069-380">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-380">Int64</span></span>|  
|<span data-ttu-id="21069-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="21069-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="21069-382">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-382">Int32</span></span>|  
|<span data-ttu-id="21069-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="21069-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="21069-384">Int16</span><span class="sxs-lookup"><span data-stu-id="21069-384">Int16</span></span>|  
|<span data-ttu-id="21069-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="21069-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="21069-386">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-386">Int64</span></span>|  
|<span data-ttu-id="21069-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="21069-388">String</span><span class="sxs-lookup"><span data-stu-id="21069-388">String</span></span>|  
|<span data-ttu-id="21069-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="21069-390">String</span><span class="sxs-lookup"><span data-stu-id="21069-390">String</span></span>|  
|<span data-ttu-id="21069-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="21069-392">String</span><span class="sxs-lookup"><span data-stu-id="21069-392">String</span></span>|  
|<span data-ttu-id="21069-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="21069-394">String</span><span class="sxs-lookup"><span data-stu-id="21069-394">String</span></span>|  
|<span data-ttu-id="21069-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="21069-396">String</span><span class="sxs-lookup"><span data-stu-id="21069-396">String</span></span>|  
|<span data-ttu-id="21069-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-397">COLLATION_NAME</span></span>|<span data-ttu-id="21069-398">String</span><span class="sxs-lookup"><span data-stu-id="21069-398">String</span></span>|  
|<span data-ttu-id="21069-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="21069-400">String</span><span class="sxs-lookup"><span data-stu-id="21069-400">String</span></span>|  
|<span data-ttu-id="21069-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="21069-402">String</span><span class="sxs-lookup"><span data-stu-id="21069-402">String</span></span>|  
|<span data-ttu-id="21069-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-403">DOMAIN_NAME</span></span>|<span data-ttu-id="21069-404">String</span><span class="sxs-lookup"><span data-stu-id="21069-404">String</span></span>|  
|<span data-ttu-id="21069-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-405">DESCRIPTION</span></span>|<span data-ttu-id="21069-406">String</span><span class="sxs-lookup"><span data-stu-id="21069-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="21069-407">Процедуры</span><span class="sxs-lookup"><span data-stu-id="21069-407">Procedures</span></span>  
  
|<span data-ttu-id="21069-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-408">ColumnName</span></span>|<span data-ttu-id="21069-409">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="21069-411">String</span><span class="sxs-lookup"><span data-stu-id="21069-411">String</span></span>|  
|<span data-ttu-id="21069-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="21069-413">String</span><span class="sxs-lookup"><span data-stu-id="21069-413">String</span></span>|  
|<span data-ttu-id="21069-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="21069-415">String</span><span class="sxs-lookup"><span data-stu-id="21069-415">String</span></span>|  
|<span data-ttu-id="21069-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="21069-417">Int16</span><span class="sxs-lookup"><span data-stu-id="21069-417">Int16</span></span>|  
|<span data-ttu-id="21069-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="21069-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="21069-419">String</span><span class="sxs-lookup"><span data-stu-id="21069-419">String</span></span>|  
|<span data-ttu-id="21069-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-420">DESCRIPTION</span></span>|<span data-ttu-id="21069-421">String</span><span class="sxs-lookup"><span data-stu-id="21069-421">String</span></span>|  
|<span data-ttu-id="21069-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="21069-422">DATE_CREATED</span></span>|<span data-ttu-id="21069-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-423">DateTime</span></span>|  
|<span data-ttu-id="21069-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="21069-424">DATE_MODIFIED</span></span>|<span data-ttu-id="21069-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="21069-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="21069-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="21069-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-427">ColumnName</span></span>|<span data-ttu-id="21069-428">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="21069-430">String</span><span class="sxs-lookup"><span data-stu-id="21069-430">String</span></span>|  
|<span data-ttu-id="21069-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="21069-432">String</span><span class="sxs-lookup"><span data-stu-id="21069-432">String</span></span>|  
|<span data-ttu-id="21069-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="21069-434">String</span><span class="sxs-lookup"><span data-stu-id="21069-434">String</span></span>|  
|<span data-ttu-id="21069-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-435">COLUMN_NAME</span></span>|<span data-ttu-id="21069-436">String</span><span class="sxs-lookup"><span data-stu-id="21069-436">String</span></span>|  
|<span data-ttu-id="21069-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-437">COLUMN_GUID</span></span>|<span data-ttu-id="21069-438">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-438">Guid</span></span>|  
|<span data-ttu-id="21069-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="21069-439">COLUMN_PROPID</span></span>|<span data-ttu-id="21069-440">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-440">Int64</span></span>|  
|<span data-ttu-id="21069-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="21069-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="21069-442">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-442">Int64</span></span>|  
|<span data-ttu-id="21069-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="21069-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="21069-444">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-444">Int64</span></span>|  
|<span data-ttu-id="21069-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="21069-445">IS_NULLABLE</span></span>|<span data-ttu-id="21069-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-446">Boolean</span></span>|  
|<span data-ttu-id="21069-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-447">DATA_TYPE</span></span>|<span data-ttu-id="21069-448">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-448">Int32</span></span>|  
|<span data-ttu-id="21069-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-449">TYPE_GUID</span></span>|<span data-ttu-id="21069-450">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-450">Guid</span></span>|  
|<span data-ttu-id="21069-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="21069-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="21069-452">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-452">Int64</span></span>|  
|<span data-ttu-id="21069-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="21069-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="21069-454">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-454">Int64</span></span>|  
|<span data-ttu-id="21069-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="21069-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="21069-456">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-456">Int32</span></span>|  
|<span data-ttu-id="21069-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="21069-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="21069-458">Int16</span><span class="sxs-lookup"><span data-stu-id="21069-458">Int16</span></span>|  
|<span data-ttu-id="21069-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-459">DESCRIPTION</span></span>|<span data-ttu-id="21069-460">String</span><span class="sxs-lookup"><span data-stu-id="21069-460">String</span></span>|  
|<span data-ttu-id="21069-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="21069-461">OVERLOAD</span></span>|<span data-ttu-id="21069-462">Int16</span><span class="sxs-lookup"><span data-stu-id="21069-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="21069-463">Представления</span><span class="sxs-lookup"><span data-stu-id="21069-463">Views</span></span>  
  
|<span data-ttu-id="21069-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-464">ColumnName</span></span>|<span data-ttu-id="21069-465">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-466">TABLE_CATALOG</span></span>|<span data-ttu-id="21069-467">String</span><span class="sxs-lookup"><span data-stu-id="21069-467">String</span></span>|  
|<span data-ttu-id="21069-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="21069-469">String</span><span class="sxs-lookup"><span data-stu-id="21069-469">String</span></span>|  
|<span data-ttu-id="21069-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-470">TABLE_NAME</span></span>|<span data-ttu-id="21069-471">String</span><span class="sxs-lookup"><span data-stu-id="21069-471">String</span></span>|  
|<span data-ttu-id="21069-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="21069-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="21069-473">String</span><span class="sxs-lookup"><span data-stu-id="21069-473">String</span></span>|  
|<span data-ttu-id="21069-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="21069-474">CHECK_OPTION</span></span>|<span data-ttu-id="21069-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-475">Boolean</span></span>|  
|<span data-ttu-id="21069-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="21069-476">IS_UPDATABLE</span></span>|<span data-ttu-id="21069-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-477">Boolean</span></span>|  
|<span data-ttu-id="21069-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-478">DESCRIPTION</span></span>|<span data-ttu-id="21069-479">String</span><span class="sxs-lookup"><span data-stu-id="21069-479">String</span></span>|  
|<span data-ttu-id="21069-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="21069-480">DATE_CREATED</span></span>|<span data-ttu-id="21069-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-481">DateTime</span></span>|  
|<span data-ttu-id="21069-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="21069-482">DATE_MODIFIED</span></span>|<span data-ttu-id="21069-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="21069-484">Индексы</span><span class="sxs-lookup"><span data-stu-id="21069-484">Indexes</span></span>  
  
|<span data-ttu-id="21069-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-485">ColumnName</span></span>|<span data-ttu-id="21069-486">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-487">TABLE_CATALOG</span></span>|<span data-ttu-id="21069-488">String</span><span class="sxs-lookup"><span data-stu-id="21069-488">String</span></span>|  
|<span data-ttu-id="21069-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="21069-490">String</span><span class="sxs-lookup"><span data-stu-id="21069-490">String</span></span>|  
|<span data-ttu-id="21069-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-491">TABLE_NAME</span></span>|<span data-ttu-id="21069-492">String</span><span class="sxs-lookup"><span data-stu-id="21069-492">String</span></span>|  
|<span data-ttu-id="21069-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-493">INDEX_CATALOG</span></span>|<span data-ttu-id="21069-494">String</span><span class="sxs-lookup"><span data-stu-id="21069-494">String</span></span>|  
|<span data-ttu-id="21069-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="21069-496">String</span><span class="sxs-lookup"><span data-stu-id="21069-496">String</span></span>|  
|<span data-ttu-id="21069-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-497">INDEX_NAME</span></span>|<span data-ttu-id="21069-498">String</span><span class="sxs-lookup"><span data-stu-id="21069-498">String</span></span>|  
|<span data-ttu-id="21069-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="21069-499">PRIMARY_KEY</span></span>|<span data-ttu-id="21069-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-500">Boolean</span></span>|  
|<span data-ttu-id="21069-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="21069-501">UNIQUE</span></span>|<span data-ttu-id="21069-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-502">Boolean</span></span>|  
|<span data-ttu-id="21069-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="21069-503">CLUSTERED</span></span>|<span data-ttu-id="21069-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-504">Boolean</span></span>|  
|<span data-ttu-id="21069-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-505">TYPE</span></span>|<span data-ttu-id="21069-506">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-506">Int32</span></span>|  
|<span data-ttu-id="21069-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="21069-507">FILL_FACTOR</span></span>|<span data-ttu-id="21069-508">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-508">Int32</span></span>|  
|<span data-ttu-id="21069-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="21069-509">INITIAL_SIZE</span></span>|<span data-ttu-id="21069-510">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-510">Int32</span></span>|  
|<span data-ttu-id="21069-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="21069-511">NULLS</span></span>|<span data-ttu-id="21069-512">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-512">Int32</span></span>|  
|<span data-ttu-id="21069-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="21069-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="21069-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-514">Boolean</span></span>|  
|<span data-ttu-id="21069-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="21069-515">AUTO_UPDATE</span></span>|<span data-ttu-id="21069-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-516">Boolean</span></span>|  
|<span data-ttu-id="21069-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="21069-517">NULL_COLLATION</span></span>|<span data-ttu-id="21069-518">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-518">Int32</span></span>|  
|<span data-ttu-id="21069-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="21069-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="21069-520">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-520">Int64</span></span>|  
|<span data-ttu-id="21069-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-521">COLUMN_NAME</span></span>|<span data-ttu-id="21069-522">String</span><span class="sxs-lookup"><span data-stu-id="21069-522">String</span></span>|  
|<span data-ttu-id="21069-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-523">COLUMN_GUID</span></span>|<span data-ttu-id="21069-524">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-524">Guid</span></span>|  
|<span data-ttu-id="21069-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="21069-525">COLUMN_PROPID</span></span>|<span data-ttu-id="21069-526">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-526">Int64</span></span>|  
|<span data-ttu-id="21069-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="21069-527">COLLATION</span></span>|<span data-ttu-id="21069-528">Int16</span><span class="sxs-lookup"><span data-stu-id="21069-528">Int16</span></span>|  
|<span data-ttu-id="21069-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="21069-529">CARDINALITY</span></span>|<span data-ttu-id="21069-530">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="21069-530">Decimal</span></span>|  
|<span data-ttu-id="21069-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="21069-531">PAGES</span></span>|<span data-ttu-id="21069-532">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-532">Int32</span></span>|  
|<span data-ttu-id="21069-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="21069-533">FILTER_CONDITION</span></span>|<span data-ttu-id="21069-534">String</span><span class="sxs-lookup"><span data-stu-id="21069-534">String</span></span>|  
|<span data-ttu-id="21069-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="21069-535">INTEGRATED</span></span>|<span data-ttu-id="21069-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="21069-537">Поставщик OLE DB для Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="21069-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="21069-538">Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="21069-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="21069-539">Таблицы</span><span class="sxs-lookup"><span data-stu-id="21069-539">Tables</span></span>  
  
-   <span data-ttu-id="21069-540">Столбцы</span><span class="sxs-lookup"><span data-stu-id="21069-540">Columns</span></span>  
  
-   <span data-ttu-id="21069-541">Процедуры</span><span class="sxs-lookup"><span data-stu-id="21069-541">Procedures</span></span>  
  
-   <span data-ttu-id="21069-542">Представления</span><span class="sxs-lookup"><span data-stu-id="21069-542">Views</span></span>  
  
-   <span data-ttu-id="21069-543">Индексы</span><span class="sxs-lookup"><span data-stu-id="21069-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="21069-544">Таблицы</span><span class="sxs-lookup"><span data-stu-id="21069-544">Tables</span></span>  
  
|<span data-ttu-id="21069-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-545">ColumnName</span></span>|<span data-ttu-id="21069-546">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-547">TABLE_CATALOG</span></span>|<span data-ttu-id="21069-548">String</span><span class="sxs-lookup"><span data-stu-id="21069-548">String</span></span>|  
|<span data-ttu-id="21069-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="21069-550">String</span><span class="sxs-lookup"><span data-stu-id="21069-550">String</span></span>|  
|<span data-ttu-id="21069-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-551">TABLE_NAME</span></span>|<span data-ttu-id="21069-552">String</span><span class="sxs-lookup"><span data-stu-id="21069-552">String</span></span>|  
|<span data-ttu-id="21069-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-553">TABLE_TYPE</span></span>|<span data-ttu-id="21069-554">String</span><span class="sxs-lookup"><span data-stu-id="21069-554">String</span></span>|  
|<span data-ttu-id="21069-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-555">TABLE_GUID</span></span>|<span data-ttu-id="21069-556">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-556">Guid</span></span>|  
|<span data-ttu-id="21069-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-557">DESCRIPTION</span></span>|<span data-ttu-id="21069-558">String</span><span class="sxs-lookup"><span data-stu-id="21069-558">String</span></span>|  
|<span data-ttu-id="21069-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="21069-559">TABLE_PROPID</span></span>|<span data-ttu-id="21069-560">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-560">Int64</span></span>|  
|<span data-ttu-id="21069-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="21069-561">DATE_CREATED</span></span>|<span data-ttu-id="21069-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-562">DateTime</span></span>|  
|<span data-ttu-id="21069-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="21069-563">DATE_MODIFIED</span></span>|<span data-ttu-id="21069-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="21069-565">Столбцы</span><span class="sxs-lookup"><span data-stu-id="21069-565">Columns</span></span>  
  
|<span data-ttu-id="21069-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-566">ColumnName</span></span>|<span data-ttu-id="21069-567">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-568">TABLE_CATALOG</span></span>|<span data-ttu-id="21069-569">String</span><span class="sxs-lookup"><span data-stu-id="21069-569">String</span></span>|  
|<span data-ttu-id="21069-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="21069-571">String</span><span class="sxs-lookup"><span data-stu-id="21069-571">String</span></span>|  
|<span data-ttu-id="21069-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-572">TABLE_NAME</span></span>|<span data-ttu-id="21069-573">String</span><span class="sxs-lookup"><span data-stu-id="21069-573">String</span></span>|  
|<span data-ttu-id="21069-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-574">COLUMN_NAME</span></span>|<span data-ttu-id="21069-575">String</span><span class="sxs-lookup"><span data-stu-id="21069-575">String</span></span>|  
|<span data-ttu-id="21069-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-576">COLUMN_GUID</span></span>|<span data-ttu-id="21069-577">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-577">Guid</span></span>|  
|<span data-ttu-id="21069-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="21069-578">COLUMN_PROPID</span></span>|<span data-ttu-id="21069-579">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-579">Int64</span></span>|  
|<span data-ttu-id="21069-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="21069-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="21069-581">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-581">Int64</span></span>|  
|<span data-ttu-id="21069-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="21069-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="21069-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-583">Boolean</span></span>|  
|<span data-ttu-id="21069-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="21069-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="21069-585">String</span><span class="sxs-lookup"><span data-stu-id="21069-585">String</span></span>|  
|<span data-ttu-id="21069-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="21069-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="21069-587">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-587">Int64</span></span>|  
|<span data-ttu-id="21069-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="21069-588">IS_NULLABLE</span></span>|<span data-ttu-id="21069-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-589">Boolean</span></span>|  
|<span data-ttu-id="21069-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-590">DATA_TYPE</span></span>|<span data-ttu-id="21069-591">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-591">Int32</span></span>|  
|<span data-ttu-id="21069-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-592">TYPE_GUID</span></span>|<span data-ttu-id="21069-593">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-593">Guid</span></span>|  
|<span data-ttu-id="21069-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="21069-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="21069-595">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-595">Int64</span></span>|  
|<span data-ttu-id="21069-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="21069-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="21069-597">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-597">Int64</span></span>|  
|<span data-ttu-id="21069-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="21069-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="21069-599">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-599">Int32</span></span>|  
|<span data-ttu-id="21069-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="21069-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="21069-601">Int16</span><span class="sxs-lookup"><span data-stu-id="21069-601">Int16</span></span>|  
|<span data-ttu-id="21069-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="21069-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="21069-603">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-603">Int64</span></span>|  
|<span data-ttu-id="21069-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="21069-605">String</span><span class="sxs-lookup"><span data-stu-id="21069-605">String</span></span>|  
|<span data-ttu-id="21069-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="21069-607">String</span><span class="sxs-lookup"><span data-stu-id="21069-607">String</span></span>|  
|<span data-ttu-id="21069-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="21069-609">String</span><span class="sxs-lookup"><span data-stu-id="21069-609">String</span></span>|  
|<span data-ttu-id="21069-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="21069-611">String</span><span class="sxs-lookup"><span data-stu-id="21069-611">String</span></span>|  
|<span data-ttu-id="21069-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="21069-613">String</span><span class="sxs-lookup"><span data-stu-id="21069-613">String</span></span>|  
|<span data-ttu-id="21069-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-614">COLLATION_NAME</span></span>|<span data-ttu-id="21069-615">String</span><span class="sxs-lookup"><span data-stu-id="21069-615">String</span></span>|  
|<span data-ttu-id="21069-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="21069-617">String</span><span class="sxs-lookup"><span data-stu-id="21069-617">String</span></span>|  
|<span data-ttu-id="21069-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="21069-619">String</span><span class="sxs-lookup"><span data-stu-id="21069-619">String</span></span>|  
|<span data-ttu-id="21069-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-620">DOMAIN_NAME</span></span>|<span data-ttu-id="21069-621">String</span><span class="sxs-lookup"><span data-stu-id="21069-621">String</span></span>|  
|<span data-ttu-id="21069-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-622">DESCRIPTION</span></span>|<span data-ttu-id="21069-623">String</span><span class="sxs-lookup"><span data-stu-id="21069-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="21069-624">Процедуры</span><span class="sxs-lookup"><span data-stu-id="21069-624">Procedures</span></span>  
  
|<span data-ttu-id="21069-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-625">ColumnName</span></span>|<span data-ttu-id="21069-626">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="21069-628">String</span><span class="sxs-lookup"><span data-stu-id="21069-628">String</span></span>|  
|<span data-ttu-id="21069-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="21069-630">String</span><span class="sxs-lookup"><span data-stu-id="21069-630">String</span></span>|  
|<span data-ttu-id="21069-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="21069-632">String</span><span class="sxs-lookup"><span data-stu-id="21069-632">String</span></span>|  
|<span data-ttu-id="21069-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="21069-634">Int16</span><span class="sxs-lookup"><span data-stu-id="21069-634">Int16</span></span>|  
|<span data-ttu-id="21069-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="21069-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="21069-636">String</span><span class="sxs-lookup"><span data-stu-id="21069-636">String</span></span>|  
|<span data-ttu-id="21069-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-637">DESCRIPTION</span></span>|<span data-ttu-id="21069-638">String</span><span class="sxs-lookup"><span data-stu-id="21069-638">String</span></span>|  
|<span data-ttu-id="21069-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="21069-639">DATE_CREATED</span></span>|<span data-ttu-id="21069-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-640">DateTime</span></span>|  
|<span data-ttu-id="21069-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="21069-641">DATE_MODIFIED</span></span>|<span data-ttu-id="21069-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="21069-643">Представления</span><span class="sxs-lookup"><span data-stu-id="21069-643">Views</span></span>  
  
|<span data-ttu-id="21069-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-644">ColumnName</span></span>|<span data-ttu-id="21069-645">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-646">TABLE_CATALOG</span></span>|<span data-ttu-id="21069-647">String</span><span class="sxs-lookup"><span data-stu-id="21069-647">String</span></span>|  
|<span data-ttu-id="21069-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="21069-649">String</span><span class="sxs-lookup"><span data-stu-id="21069-649">String</span></span>|  
|<span data-ttu-id="21069-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-650">TABLE_NAME</span></span>|<span data-ttu-id="21069-651">String</span><span class="sxs-lookup"><span data-stu-id="21069-651">String</span></span>|  
|<span data-ttu-id="21069-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="21069-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="21069-653">String</span><span class="sxs-lookup"><span data-stu-id="21069-653">String</span></span>|  
|<span data-ttu-id="21069-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="21069-654">CHECK_OPTION</span></span>|<span data-ttu-id="21069-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-655">Boolean</span></span>|  
|<span data-ttu-id="21069-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="21069-656">IS_UPDATABLE</span></span>|<span data-ttu-id="21069-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-657">Boolean</span></span>|  
|<span data-ttu-id="21069-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21069-658">DESCRIPTION</span></span>|<span data-ttu-id="21069-659">String</span><span class="sxs-lookup"><span data-stu-id="21069-659">String</span></span>|  
|<span data-ttu-id="21069-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="21069-660">DATE_CREATED</span></span>|<span data-ttu-id="21069-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-661">DateTime</span></span>|  
|<span data-ttu-id="21069-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="21069-662">DATE_MODIFIED</span></span>|<span data-ttu-id="21069-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="21069-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="21069-664">Индексы</span><span class="sxs-lookup"><span data-stu-id="21069-664">Indexes</span></span>  
  
|<span data-ttu-id="21069-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="21069-665">ColumnName</span></span>|<span data-ttu-id="21069-666">DataType</span><span class="sxs-lookup"><span data-stu-id="21069-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="21069-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-667">TABLE_CATALOG</span></span>|<span data-ttu-id="21069-668">String</span><span class="sxs-lookup"><span data-stu-id="21069-668">String</span></span>|  
|<span data-ttu-id="21069-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="21069-670">String</span><span class="sxs-lookup"><span data-stu-id="21069-670">String</span></span>|  
|<span data-ttu-id="21069-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-671">TABLE_NAME</span></span>|<span data-ttu-id="21069-672">String</span><span class="sxs-lookup"><span data-stu-id="21069-672">String</span></span>|  
|<span data-ttu-id="21069-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="21069-673">INDEX_CATALOG</span></span>|<span data-ttu-id="21069-674">String</span><span class="sxs-lookup"><span data-stu-id="21069-674">String</span></span>|  
|<span data-ttu-id="21069-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="21069-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="21069-676">String</span><span class="sxs-lookup"><span data-stu-id="21069-676">String</span></span>|  
|<span data-ttu-id="21069-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-677">INDEX_NAME</span></span>|<span data-ttu-id="21069-678">String</span><span class="sxs-lookup"><span data-stu-id="21069-678">String</span></span>|  
|<span data-ttu-id="21069-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="21069-679">PRIMARY_KEY</span></span>|<span data-ttu-id="21069-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-680">Boolean</span></span>|  
|<span data-ttu-id="21069-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="21069-681">UNIQUE</span></span>|<span data-ttu-id="21069-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-682">Boolean</span></span>|  
|<span data-ttu-id="21069-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="21069-683">CLUSTERED</span></span>|<span data-ttu-id="21069-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-684">Boolean</span></span>|  
|<span data-ttu-id="21069-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="21069-685">TYPE</span></span>|<span data-ttu-id="21069-686">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-686">Int32</span></span>|  
|<span data-ttu-id="21069-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="21069-687">FILL_FACTOR</span></span>|<span data-ttu-id="21069-688">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-688">Int32</span></span>|  
|<span data-ttu-id="21069-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="21069-689">INITIAL_SIZE</span></span>|<span data-ttu-id="21069-690">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-690">Int32</span></span>|  
|<span data-ttu-id="21069-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="21069-691">NULLS</span></span>|<span data-ttu-id="21069-692">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-692">Int32</span></span>|  
|<span data-ttu-id="21069-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="21069-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="21069-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-694">Boolean</span></span>|  
|<span data-ttu-id="21069-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="21069-695">AUTO_UPDATE</span></span>|<span data-ttu-id="21069-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-696">Boolean</span></span>|  
|<span data-ttu-id="21069-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="21069-697">NULL_COLLATION</span></span>|<span data-ttu-id="21069-698">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-698">Int32</span></span>|  
|<span data-ttu-id="21069-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="21069-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="21069-700">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-700">Int64</span></span>|  
|<span data-ttu-id="21069-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="21069-701">COLUMN_NAME</span></span>|<span data-ttu-id="21069-702">String</span><span class="sxs-lookup"><span data-stu-id="21069-702">String</span></span>|  
|<span data-ttu-id="21069-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="21069-703">COLUMN_GUID</span></span>|<span data-ttu-id="21069-704">Guid</span><span class="sxs-lookup"><span data-stu-id="21069-704">Guid</span></span>|  
|<span data-ttu-id="21069-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="21069-705">COLUMN_PROPID</span></span>|<span data-ttu-id="21069-706">Int64</span><span class="sxs-lookup"><span data-stu-id="21069-706">Int64</span></span>|  
|<span data-ttu-id="21069-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="21069-707">COLLATION</span></span>|<span data-ttu-id="21069-708">Int16</span><span class="sxs-lookup"><span data-stu-id="21069-708">Int16</span></span>|  
|<span data-ttu-id="21069-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="21069-709">CARDINALITY</span></span>|<span data-ttu-id="21069-710">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="21069-710">Decimal</span></span>|  
|<span data-ttu-id="21069-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="21069-711">PAGES</span></span>|<span data-ttu-id="21069-712">Int32</span><span class="sxs-lookup"><span data-stu-id="21069-712">Int32</span></span>|  
|<span data-ttu-id="21069-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="21069-713">FILTER_CONDITION</span></span>|<span data-ttu-id="21069-714">String</span><span class="sxs-lookup"><span data-stu-id="21069-714">String</span></span>|  
|<span data-ttu-id="21069-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="21069-715">INTEGRATED</span></span>|<span data-ttu-id="21069-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="21069-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21069-717">См. также</span><span class="sxs-lookup"><span data-stu-id="21069-717">See also</span></span>

- [<span data-ttu-id="21069-718">Управляемые поставщики ADO.NET и центр разработчиков DataSet</span><span class="sxs-lookup"><span data-stu-id="21069-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
