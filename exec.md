Exec examples
=============

# simple sync : 1 domain, change, add
These execution will 

- get the documents of LAB domain (2 docs)
- get the documents of PALM domain : delete LAB docs, download PALM docs
- add the documents of PAT domain

On windows plateform

    PS C:\doc\ihe-tf> Invoke-WebRequest -Uri https://raw.githubusercontent.com/flrt/ihe-tf-sync/master/sync.ps1 -OutFile syn
    c.ps1
    PS C:\doc\ihe-tf> .\sync.ps1 LAB
    Sync domains : LAB
    Get information about documents
    ..
    223 documents found in IHE website.
    TF: 8 documents
    PAT: 3 documents
    CARD: 17 documents
    DENT: 1 documents
    ENDO: 2 documents
    EYECARE: 6 documents
    ITI: 41 documents
    LAB: 2 documents
    PALM: 7 documents
    PCC: 39 documents
    PHDSC: 2 documents
    PCD: 15 documents
    SUPPL: 2 documents
    PHARMACY: 11 documents
    QRPH: 26 documents
    QUALITY: 1 documents
    RO: 5 documents
    RAD: 35 documents
    
    Clean documents not in sync...
    
    Syncing LAB domain...
    Newer document IHE_LAB_Suppl_GIR_Rev1-1_TI_2010-10_15.pdf found: download it...
    Newer document IHE_LAB_Suppl_ILW.pdf found: download it...
    
![step 1](doc/step1-LAB.png)

    PS C:\doc\ihe-tf> .\sync.ps1 PALM
    Sync domains : PALM
    Get information about documents
    .......
    223 documents found in IHE website.
    TF: 8 documents
    PAT: 3 documents
    CARD: 17 documents
    DENT: 1 documents
    ENDO: 2 documents
    EYECARE: 6 documents
    ITI: 41 documents
    LAB: 2 documents
    PALM: 7 documents
    PCC: 39 documents
    PHDSC: 2 documents
    PCD: 15 documents
    SUPPL: 2 documents
    PHARMACY: 11 documents
    QRPH: 26 documents
    QUALITY: 1 documents
    RO: 5 documents
    RAD: 35 documents
    
    Clean documents not in sync...
    Obsolete document IHE_LAB_Suppl_GIR_Rev1-1_TI_2010-10_15.pdf found: delete it...
    Obsolete document IHE_LAB_Suppl_ILW.pdf found: delete it...
    
    Syncing PALM domain...
    Newer document IHE_PaLM_TF_Vol1.pdf found: download it...
    Newer document IHE_PaLM_TF_Vol2a.pdf found: download it...
    Newer document IHE_PaLM_TF_Vol2b.pdf found: download it...
    Newer document IHE_PaLM_TF_Vol2c.pdf found: download it...
    Newer document IHE_PaLM_TF_Vol2x.pdf found: download it...
    Newer document IHE_PaLM_TF_Vol3.pdf found: download it...
    Newer document IHE_PaLM_Suppl_APSR.pdf found: download it...
    PS C:\doc\ihe-tf>

![step 2](doc/step2-PALM.png)

    PS C:\doc\ihe-tf> .\sync.ps1 PALM,PAT
    Sync domains : PALM,PAT
    Get information about documents
    ..........
    223 documents found in IHE website.
    TF: 8 documents
    PAT: 3 documents
    CARD: 17 documents
    DENT: 1 documents
    ENDO: 2 documents
    EYECARE: 6 documents
    ITI: 41 documents
    LAB: 2 documents
    PALM: 7 documents
    PCC: 39 documents
    PHDSC: 2 documents
    PCD: 15 documents
    SUPPL: 2 documents
    PHARMACY: 11 documents
    QRPH: 26 documents
    QUALITY: 1 documents
    RO: 5 documents
    RAD: 35 documents
    
    Clean documents not in sync...
    
    Syncing PAT domain...
    Newer document IHE_PAT_TF_Rev2-0_Vol1_TI_2010-07-23.pdf found: download it...
    Newer document IHE_PAT_TF_Rev2-0_Vol2_TI_2010-07-23.pdf found: download it...
    Newer document IHE_PAT_Suppl_ARPH_Rev2-0_TI_2010-07-23.pdf found: download it...
    
    Syncing PALM domain...
    PS C:\doc\ihe-tf>
 
![step 3](doc/step3-PAT.png)

# global Synchro : all domains

On macOs (or Linux)

    $ curl -O https://raw.githubusercontent.com/flrt/ihe-tf-sync/master/sync.sh
    $ sh sync.sh
    Get information about documents
    .................................................................................................................................................................................................................................
    223 documents found in IHE website.
    TF: 8 documents
    PAT: 3 documents
    CARD: 17 documents
    DENT: 1 documents
    ENDO: 2 documents
    EYECARE: 6 documents
    ITI: 41 documents
    LAB: 2 documents
    PALM: 7 documents
    PCC: 39 documents
    PHDSC: 2 documents
    PCD: 15 documents
    SUPPL: 2 documents
    PHARMACY: 11 documents
    QRPH: 26 documents
    QUALITY: 1 documents
    RO: 5 documents
    RAD: 35 documents
    
    Clean documents not in sync...
    
    Syncing TF domain...
    Newer document IHE_TF_GenIntro_Rev1.1_2018-03-09.pdf found: download it...
    Newer document IHE_TF_GenIntro_AppA_Actors_Rev2.0_2018-03-09.pdf found: download it...
    Newer document IHE_TF_GenIntro_AppB_Transactions_Rev1.0_2018-03-09.pdf found: download it...
    Newer document IHE_TF_GenIntro_AppC_Namespaces_Rev1.0_2018-03-09.pdf found: download it...
    Newer document IHE_TF_GenIntro_AppD_Glossary_Rev2.0_2018-03-09.pdf found: download it...
    Newer document IHE_TF_GenIntro_AppE_Profiling_Rev1.1_2018-03-09.pdf found: download it...
    Newer document IHE_TF_GenIntro_AppF_IHEIntegrationStatements_Rev1.1_2018-03-09.pdf found: download it...
    Newer document ihe_tf_whitepaper_DWF_TI-draft-2004-04-15.pdf found: download it...
    
    Syncing PAT domain...
    Newer document IHE_PAT_TF_Rev2-0_Vol1_TI_2010-07-23.pdf found: download it...
    Newer document IHE_PAT_TF_Rev2-0_Vol2_TI_2010-07-23.pdf found: download it...
    Newer document IHE_PAT_Suppl_ARPH_Rev2-0_TI_2010-07-23.pdf found: download it...
    
    Syncing CARD domain...
    Newer document IHE_CARD_TF_Vol1.pdf found: download it...
    Newer document IHE_CARD_TF_Vol2.pdf found: download it...
    Newer document IHE_CARD_Suppl_CIRC_Rev1-1_TI-2011-07-01.pdf found: download it...
    Newer document IHE_Card_Suppl_CPN.pdf found: download it...
    Newer document IHE_CARD_Suppl_CRC.pdf found: download it...
    Newer document IHE_CARD_Suppl_DRPT.pdf found: download it...
    Newer document IHE_CARD_Suppl_ED.pdf found: download it...
    Newer document IHE_CARD_Suppl_EPRC-IE.pdf found: download it...
    Newer document IHE_CARD_Suppl_IEO.pdf found: download it...
    Newer document IHE_CARD_Suppl_IVI_Option_for_Cath_Workflow.pdf found: download it...
    Newer document IHE_CARD_Suppl_RCS-C.pdf found: download it...
    Newer document IHE_CARD_Suppl_RCS-C_Rev1.1_TI_2014-07-18_SampleDataCollectionForm.pdf found: download it...
    Newer document IHE_CARD_Suppl_RCS-EP.pdf found: download it...
    Newer document IHE_CARD_Suppl_REWF.pdf found: download it...
    Newer document IHE_CARD_Suppl_Stress.pdf found: download it...
    Newer document IHE_CARD_WP_3DEcho_Rev1.0_2011-08-05.pdf found: download it...
    Newer document IHE_CARD_TF_White_Paper_Cardiology_Data_Handling_Final.pdf found: download it...
    
    Syncing DENT domain...
    
    Syncing ENDO domain...
    Newer document IHE_ENDO_Suppl_ERPO.pdf found: download it...
    Newer document IHE_ENDO_Suppl_EWF.pdf found: download it...
    
    Syncing EYECARE domain...
    Newer document IHE_EyeCare_TF_Vol1.pdf found: download it...
    Newer document IHE_EyeCare_TF_Vol2.pdf found: download it...
    Newer document IHE_EyeCare_Suppl_CCDA_GEE.pdf found: download it...
    Newer document IHE_EyeCare_Suppl_EC-Summary.pdf found: download it...
    Newer document IHE_EyeCare_Suppl_U-EYECARE_Refractive.pdf found: download it...
    Newer document IHE_Eye_Care_TF_Supplement_Appointment_Scheduling_TI_2010-05-03.pdf found: download it...
    
    Syncing ITI domain...
    Newer document IHE_ITI_TF_Vol1.pdf found: download it...
    Newer document IHE_ITI_TF_Vol2a.pdf found: download it...
    Newer document IHE_ITI_TF_Vol2b.pdf found: download it...
    Newer document IHE_ITI_TF_Vol2x.pdf found: download it...
    Newer document IHE_ITI_TF_Vol3.pdf found: download it...
    Newer document IHE_ITI_TF_Vol4.pdf found: download it...
    Newer document IHE_ITI_Suppl_RESTful-ATNA.pdf found: download it...
    Newer document IHE_ITI_Suppl_APPC.pdf found: download it...
    Newer document IHE_ITI_Suppl_Appx-Z.pdf found: download it...
    Newer document IHE_ITI_Suppl_AsyncAS4Option.pdf found: download it...
    Newer document IHE_ITI_Suppl_CSD.pdf found: download it...
    Newer document IHE_ITI_Suppl_XCDR.pdf found: download it...
    Newer document IHE_ITI_Suppl_XCF.pdf found: download it...
    Newer document IHE_ITI_Suppl_XCPD_HDL_Revoke_Option.pdf found: download it...
    Newer document IHE_ITI_Suppl_XDW_for_XCA_and_XCDR.pdf found: download it...
    Newer document IHE_ITI_Suppl_DEN.pdf found: download it...
    Newer document IHE_ITI_Suppl_DSUB_Extensions.pdf found: download it...
    Newer document IHE_ITI_Suppl_HPD.pdf found: download it...
    Newer document IHE_ITI_Suppl_IUA.pdf found: download it...
    Newer document IHE_ITI_Suppl_MHD.pdf found: download it...
    Newer document IHE_ITI_Suppl_mACM.pdf found: download it...
    Newer document IHE_ITI_Suppl_mCSD.pdf found: download it...
    Newer document IHE_ITI_Suppl_mXDE.pdf found: download it...
    Newer document IHE_ITI_Suppl_NPFSm.pdf found: download it...
    Newer document IHE_ITI_Suppl_PDQm.pdf found: download it...
    Newer document IHE_ITI_Suppl_PIXm.pdf found: download it...
    Newer document IHE_ITI_Suppl_PLT.pdf found: download it...
    Newer document IHE_ITI_Suppl_RMD.pdf found: download it...
    Newer document IHE_ITI_Suppl_RMU.pdf found: download it...
    Newer document IHE_ITI_Suppl_SeR.pdf found: download it...
    Newer document IHE_ITI_Suppl_XPID.pdf found: download it...
    Newer document IHE_ITI_Suppl_XDS_Metadata_Update.pdf found: download it...
    Newer document IHE_ITI_Whitepaper_Security_Cookbook_2008-11-10.pdf found: download it...
    Newer document IHE_ITI_Handbook_De-Identification_Rev1.1_2014-06-06.pdf found: download it...
    Newer document IHE_ITI_Handbook_Metadata.pdf found: download it...
    Newer document IHE_ITI_White_Paper_XDS_Affinity_Domain_Template_TI_2008-12-02.pdf found: download it...
    Newer document IHE_ITI_TF_WhitePaper_AccessControl_2009-09-28.pdf found: download it...
    Newer document IHE_ITI_WP_Analysis-of-DeID-Algorithms-for-FP-Data_Elements.pdf found: download it...
    Newer document IHE_ITI_TF_WhitePaper_A-Service-Oriented-Architecture_SOA_2009-09-28.pdf found: download it...
    Newer document IHE_ITI_White-Paper_Enabling-doc-sharing-through-IHE-Profiles_Rev1-0_2012-01-24.pdf found: download it...
    Newer document IHE_ITI_WP_HITStdsforHIMPratices_Rev1.1_2015-09-18.pdf found: download it...
    
    Syncing LAB domain...
    Newer document IHE_LAB_Suppl_GIR_Rev1-1_TI_2010-10_15.pdf found: download it...
    Newer document IHE_LAB_Suppl_ILW.pdf found: download it...
    
    Syncing PALM domain...
    Newer document IHE_PaLM_TF_Vol1.pdf found: download it...
    Newer document IHE_PaLM_TF_Vol2a.pdf found: download it...
    Newer document IHE_PaLM_TF_Vol2b.pdf found: download it...
    Newer document IHE_PaLM_TF_Vol2c.pdf found: download it...
    Newer document IHE_PaLM_TF_Vol2x.pdf found: download it...
    Newer document IHE_PaLM_TF_Vol3.pdf found: download it...
    Newer document IHE_PaLM_Suppl_APSR.pdf found: download it...
    
    Syncing PCC domain...
    Newer document IHE_PCC_TF_Vol1.pdf found: download it...
    Newer document IHE_PCC_TF_Vol2.pdf found: download it...
    Newer document IHE_PCC_Suppl_360X.pdf found: download it...
    Newer document IHE_PCC_Suppl_AntepartumProfiles_Rev1-2_TI_2011-09-09.pdf found: download it...
    Newer document IHE_PCC_Suppl_BED.pdf found: download it...
    Newer document IHE_PCC_Care_Management_CM_Supplement_TI_2008-08-22.pdf found: download it...
    Newer document IHE_PCC_Suppl_CDA_Content_Modules.pdf found: download it...
    Newer document IHE_PCC_Suppl_CDA_DSS.pdf found: download it...
    Newer document IHE_PCC_Suppl_CMAP.pdf found: download it...
    Newer document IHE_PCC_Suppl_XBeR-WD.pdf found: download it...
    Newer document IHE_PCC_Suppl_XCHT-WD.pdf found: download it...
    Newer document IHE_PCC_Suppl_XTHM-WD.pdf found: download it...
    Newer document IHE_PCC_Suppl_XTB-WD.pdf found: download it...
    Newer document IHE_PCC_Suppl_DCP.pdf found: download it...
    Newer document IHE_PCC_Suppl_DCTM.pdf found: download it...
    Newer document IHE_PCC_Suppl_EDES.pdf found: download it...
    Newer document IHE_PCC_Suppl_ENS.pdf found: download it...
    Newer document IHE_PCC_Suppl_GAO.pdf found: download it...
    Newer document IHE_PCC_Suppl_Labor_and_Delivery_Profiles.pdf found: download it...
    Newer document IHE_PCC_Suppl_MCV.pdf found: download it...
    Newer document IHE_PCC_Suppl_NDS_Rev1-2_TI_2011-09-09.pdf found: download it...
    Newer document IHE_PCC_Suppl_PCS.pdf found: download it...
    Newer document IHE_PCC_Suppl_PtCP.pdf found: download it...
    Newer document IHE_PCC_Suppl_PPOC.pdf found: download it...
    Newer document IHE_PCC_Suppl_PW_Rev1-1_TI_2010-08-30.pdf found: download it...
    Newer document IHE_PCC_Suppl_PMDT.pdf found: download it...
    Newer document IHE_PCC_Suppl_PPVS_Rev1-2_TI_2011-09-09.pdf found: download it...
    Newer document IHE_PCC_Suppl_QED.pdf found: download it...
    Newer document IHE_PCC_Suppl_QEDm.pdf found: download it...
    Newer document IHE_PCC_Suppl_RECON.pdf found: download it...
    Newer document IHE_PCC_Suppl_ROL.pdf found: download it...
    Newer document IHE_PCC_Suppl_RPM.pdf found: download it...
    Newer document IHE_PCC_Request_for_Clinical_Guidance_RCG_TI_-2009-08-10.pdf found: download it...
    Newer document IHE_PCC_Suppl_RCK.pdf found: download it...
    Newer document IHE_PCC_Suppl_RIPT.pdf found: download it...
    Newer document IHE_PCC_Suppl_TransportRecordSummaryProfiles_Rev1-1_TI_2011-09-09.pdf found: download it...
    Newer document IHE_PCC_IG_DAF_National-Extension.pdf found: download it...
    Newer document IHE_PCC_White_Paper_DAF_Rev1.1_2014-10-24.pdf found: download it...
    Newer document IHE_PCC_WP_PtDemographics-PR_Rev1.1_2017-09-27.pdf found: download it...
    
    Syncing PHDSC domain...
    Newer document IHE_PHDSC_Public_Health_White_Paper_2007_10_11.pdf found: download it...
    Newer document IHE-PHDSC_Public_Health_White_Paper_2008-07-29.pdf found: download it...
    
    Syncing PCD domain...
    Newer document IHE_PCD_TF_Vol1.pdf found: download it...
    Newer document IHE_PCD_TF_Vol2.pdf found: download it...
    Newer document IHE_PCD_TF_Vol3.pdf found: download it...
    Newer document IHE_PCD_Suppl_IPEC.pdf found: download it...
    Newer document IHE_PCD_Suppl_POI.pdf found: download it...
    Newer document IHE_PCD_Suppl_RDQ.pdf found: download it...
    Newer document IHE_PCD_Suppl_SPD_Rev1-2_TI_Reissued-2011-11-11.pdf found: download it...
    Newer document IHE_PCD_Suppl_WCM.pdf found: download it...
    Newer document IHE_PCD_WP_PCIM_Rev1.1_2017-06-16.pdf found: download it...
    Newer document IHE_PCD_WP_Patching_Rev1.1_2015-10-14.pdf found: download it...
    Newer document IHE_PCD_Medical-Equipment-Management_MEM_White-Paper_V1-0_2009-09-01.pdf found: download it...
    Newer document IHE_PCD_White-Paper_MEM_Cyber_Security_Rev2-0_2011-05-27.pdf found: download it...
    Newer document IHE_PCD_WP_Cyber-Security_Rev1.1_2015-10-14.pdf found: download it...
    Newer document IHE_PCD_WP_RDC_Rev1-1_Pub_2018-10-23.pdf found: download it...
    Newer document IHE_PCD_User_Handbook_2018_Edition.pdf found: download it...
    
    Syncing SUPPL domain...
    Newer document IHE_Suppl_PCD_MEM-DMC.pdf found: download it...
    Newer document IHE_Suppl_PCD_MEM-LS.pdf found: download it...
    
    Syncing PHARMACY domain...
    Newer document IHE_Pharmacy_Suppl_Common.pdf found: download it...
    Newer document IHE_Pharmacy_Suppl_DIS.pdf found: download it...
    Newer document IHE_Pharmacy_Suppl_CMA.pdf found: download it...
    Newer document IHE_Pharmacy_Suppl_PML.pdf found: download it...
    Newer document IHE_Pharmacy_Suppl_CMPD.pdf found: download it...
    Newer document IHE_Pharmacy_Suppl_MTP.pdf found: download it...
    Newer document IHE_Pharmacy_Suppl_PADV.pdf found: download it...
    Newer document IHE_Pharmacy_Suppl_PRE.pdf found: download it...
    Newer document IHE_Pharmacy_Suppl_HMW.pdf found: download it...
    Newer document IHE_Pharm_Suppl_MMA.pdf found: download it...
    Newer document IHE_Pharm_Suppl_UBP.pdf found: download it...
    
    Syncing QRPH domain...
    Newer document IHE_QRPH_TF_Vol1.pdf found: download it...
    Newer document IHE_QRPH_TF_Vol2.pdf found: download it...
    Newer document IHE_QRPH_TF_Vol3.pdf found: download it...
    Newer document IHE_QRPH_Suppl_ADX.pdf found: download it...
    Newer document IHE_QRPH_Suppl_BFDR-E.pdf found: download it...
    Newer document IHE_QRPH_Suppl_CRPC.pdf found: download it...
    Newer document IHE_QRPH_Suppl_DEX.pdf found: download it...
    Newer document IHE_QRPH_Suppl_EHDI.pdf found: download it...
    Newer document IHE_QRPH_Suppl_EHDI-WD.pdf found: download it...
    Newer document IHE_QRPH_Suppl_FP.pdf found: download it...
    Newer document IHE_QRPH_Suppl_FPv2.pdf found: download it...
    Newer document IHE_QRPH_Suppl_HW.pdf found: download it...
    Newer document IHE_QRPH_Suppl_mRFD.pdf found: download it...
    Newer document IHE_QRPH_Suppl_NANI.pdf found: download it...
    Newer document IHE_QRPH_Suppl_PRPH_Ca_Rev2-1_2011-09-02.pdf found: download it...
    Newer document IHE_QRPH_Suppl_QME-EH.pdf found: download it...
    Newer document IHE_QRPH_Suppl_QORE.pdf found: download it...
    Newer document IHE_QRPH_Suppl_RPE.pdf found: download it...
    Newer document IHE_QRPH_Suppl_SDC.pdf found: download it...
    Newer document IHE_QRPH_Suppl_VRDR.pdf found: download it...
    Newer document IHE_QRPH_WP_eCQM_Standards.pdf found: download it...
    Newer document IHE_QRPH_WP_Diabetes_Care_Mngt_PC_2010_06_04.pdf found: download it...
    Newer document IHE_QRPH_Newborn_Screening_NBS_WhitePaper_Final_2009-09-01.pdf found: download it...
    Newer document IHE_QRPH_WP_IHE4ICP.pdf found: download it...
    Newer document IHE_QRPH_White_Paper_Perfomance_Measure_Data_Element_Structured_for_EHR_Extraction_2008-06-10.pdf found: download it...
    Newer document IHE_QRPH_WP_Healthcare_Secondary_Data_Access.pdf found: download it...
    
    Syncing QUALITY domain...
    Newer document IHE_Quality_TF_rev1.pdf found: download it...
    
    Syncing RO domain...
    Newer document IHE_RO_TF_Vol1.pdf found: download it...
    Newer document IHE_RO_TF_Vol2.pdf found: download it...
    Newer document IHE_RO_Suppl_MMRO-III.pdf found: download it...
    Newer document IHE_RO_Suppl_TDPC.pdf found: download it...
    Newer document IHE_RO_Suppl_TPPC.pdf found: download it...
    
    Syncing RAD domain...
    Newer document IHE_RAD_TF_Vol1.pdf found: download it...
    Newer document IHE_RAD_TF_Vol2.pdf found: download it...
    Newer document IHE_RAD_TF_Vol3.pdf found: download it...
    Newer document IHE_RAD_TF_Vol4.pdf found: download it...
    Newer document IHE_RAD_Suppl_BIR.pdf found: download it...
    Newer document IHE_RAD_TF_Supplement_Chest_X-Ray_CAD_Display_TI_2010-06-17.pdf found: download it...
    Newer document IHE_Rad_Suppl_CDS-OAT.pdf found: download it...
    Newer document IHE_RAD_Suppl_XDR-I.pdf found: download it...
    Newer document IHE_RAD_Suppl_XRR-WD.pdf found: download it...
    Newer document IHE_RAD_Suppl_PERF.pdf found: download it...
    Newer document IHE_RAD_Suppl_DBT.pdf found: download it...
    Newer document IHE_RAD_Suppl_EBIW.pdf found: download it...
    Newer document IHE-RAD_TF_Suppl_PDI_Extensions_2009-06-21.pdf found: download it...
    Newer document IHE_RAD-TF_Suppl_FUS_TI_2006-04-13.pdf found: download it...
    Newer document IHE_RAD_Suppl_IOCM.pdf found: download it...
    Newer document IHE_RAD_Suppl_IRWF.b.pdf found: download it...
    Newer document IHE_RAD_Suppl_IID.pdf found: download it...
    Newer document IHE_RAD_Suppl_MAWF.pdf found: download it...
    Newer document IHE_RAD_Suppl_MAP.pdf found: download it...
    Newer document IHE_RAD_Suppl_MRRT.pdf found: download it...
    Newer document IHE-RAD_TF_Suppl_DIFF_2009-06-21.pdf found: download it...
    Newer document IHE_RAD_Suppl_MIMA.pdf found: download it...
    Newer document IHE_RAD_TF_Supp_NMI_TI_2007_05_17.pdf found: download it...
    Newer document IHE_RAD_Suppl_PAWF_Rev1-1_TI_2012-06-15.pdf found: download it...
    Newer document IHE_RAD_Suppl_REM-NM.pdf found: download it...
    Newer document IHE_RAD_Supp_RRR-WF.pdf found: download it...
    Newer document IHE_RAD_Suppl_RD.pdf found: download it...
    Newer document IHE_RAD_Suppl_SWF.b.pdf found: download it...
    Newer document IHE_RAD_Suppl_SOLE.pdf found: download it...
    Newer document IHE_RAD_Suppl_SMI.pdf found: download it...
    Newer document IHE_RAD_Suppl_WIA.pdf found: download it...
    Newer document IHE_RAD_Suppl_WIC.pdf found: download it...
    Newer document IHE_RAD_White-Paper_Codes_Rev2.0_2014-03-07.pdf found: download it...
    Newer document IHE_RAD_White-Paper_XSM-WD_Rev1-0_2012-12-17.pdf found: download it...
    Newer document IHE_RAD_White-Paper_RadiologyReportTemplates_Rev1-0_2012-12-17.pdf found: download it...
