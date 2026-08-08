

# awesome-bioinformatics-tools
Una lista curada de software, herramientas y recursos excelentes de Bioinformática.

Algunas universidades e institutos de investigación también mantienen tienen listas de software y herramientas organizadas, como:

+ https://wiki.gacrc.uga.edu/wiki/Main_Page
+ https://wiki.rc.ufl.edu/doc/Category:Software
+ http://www.vcru.wisc.edu/simonlab/bioinformatics/programs/index.html

Algunos foros también tienen hilos de discusión similares, como http://seqanswers.com/wiki/Software

Recomiendo personalmente un sitio web con muchas descripciones de herramientas: https://omictools.com/


## 1. Control de Calidad (Quality Control)

- FastQC（http://www.bioinformatics.babraham.ac.uk/projects/fastqc/）
  Nota: Uso de FastQC: http://www.plob.org/2013/07/16/5987.html
- Fastx-toolkit（http://hannonlab.cshl.edu/fastx_toolkit/）
- PrinSeq（http://prinseq.sourceforge.net/）
- <s>FastUniq（https://sourceforge.net/projects/fastuniq/）: fusiona múltiples archivos fastq en 2 archivos y elimina simultáneamente las secuencias repetidas (duplicates). (Nota: fastuniq no puede leer archivos fastq comprimidos en gzip, deben descomprimirse primero).</s>
  Otras herramientas para eliminar duplicates (sin alineamiento a genoma de referencia): fastx_collapser en FASTX-Toolkit (single-end) y Fulcrum, CD-HIT-DUP, GPU-DupRemoval
  Para eliminar duplicates, consulte la referencia: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5123249/
- QUASR：https://sourceforge.net/projects/quasr/：QUASR es una canalización ligera escrita para procesar y analizar datos de secuenciación de nueva generación (NGS) de plataformas Illumina, 454 e Ion Torrent.
- RSeQC：Paquete RSeQC, proporciona una serie de herramientas herramientas útiles para evaluar datos de secuenciación de alto rendimiento, especialmente RNA-seq. Incluye Mód básico; verificar la calidad de las secuencias, sesgo de composición nucleotídica, sesgo PCR, sesgo de contenido GC, y módulos específicos para RNA-seq: evaluar la saturación de secuenciación, distribución de lecturas aline mapeadas, uniformidad de cobertura, especificidad de cadena, integridad del ARN a nivel transcripcional, etc. https://www.jianshu.com/p/edb9a5c3ecb0


## 2. Filtrado y recorte de lecturas (trim)

- Búsqueda de vectores, adaptadores, enlazadores y cebadores de PCR：https://www.ncbi.nlm.nih.gov/tools/vecscreen/
- Cutadapt: https://github.com/marcelm/cutadapt  o http://cutadapt.readthedocs.io/en/stable/index.html  elimina secuencias de adaptador
- Trimmomatic（http://www.usadellab.org/cms/?page=trimmomatic）
- sickle(https://github.com/najoshi/sickle/)
- NGSQC toolkit（http://www.nipgr.res.in/ngsqctoolkit.html）
  Nota: Uso de NGSQC toolkit: http://blog.csdn.net/shmilyringpull/article/details/9225195
- SolexaQA（http://solexaqa.sourceforge.net/  o https://sourceforge.net/projects/solexaqa/files/src/）
- Trim Galore：http://www.bioinformatics.babraham.ac.uk/projects/trim_galore/  o https://github.com/FelixKrueger/TrimGalore
- Platanus_trim：http://platanus.bio.titech.ac.jp/?page_id=30 (no admite soporta archivos fastq en formato gzip)
- Seqtk: https://github.com/lh3/seqtk
- Seqprep（https://github.com/jstjohn/SeqPrep）
- TagCleaner（https://sourceforge.net/projects/tagcleaner/files/）：elimina secuencias de etiqueta (por ejemplo, etiquetas WTA o MID) de conjuntos de datos metagenómicos. 
- BioPieces: http://code.google.com/p/biopieces/
- fastp：https://github.com/OpenGene/fastp
- SOAPnuke：https://github.com/BGI-flexlab/SOAPnuke
- seq_crumbs（https://bioinf.comav.upv.es/seq_crumbs/）(programa de Python 2, no recomendado!)
- seqcln（https://sourceforge.net/projects/seqclean/）(para formato fasta, no recomendado!)
  Comparación entre herramientas de control de calidad: https://zhuanlan.zhihu.com/p/28924793

  Secuenciación de segunda generación --- Capítulo de control de calidad, referencia: http://www.cnblogs.com/ZHshuang463508120/p/3606871.html

  
## 3. Corrección de errores de lecturas

Las herramientas relacionadas con la corrección de lecturas incluyen: SOAPec y ErrorCorrection, ambas desarrolladas por BGI, disponibles para descargar en http://soap.genomics.org.cn/soapdenovo.html.

- SOAPec_v2.01.tar.gz, una herramienta de corrección para SOAPdenovo:
  http://sourceforge.net/projects/soapdenovo2/files/ErrorCorrection/SOAPec_v2.01.tar.gz/download 
- ErrorCorrection.tgz, otra herramienta de corrección para SOAPdenovo:
  http://sourceforge.net/projects/soapdenovo2/files/ErrorCorrection/ErrorCorrection.tgz/download

- Herramienta de corrección http://soap.genomics.org.cn/down/correction.tar.gz
- SOAPdenovo http://soap.genomics.org.cn/down/SOAPdenovo-v1.04.tgz
- GapCloser http://soap.genomics.org.cn/down/GapCloser.tar.gz

Consulte https://omictools.com/error-correction-category para más herramientas de corrección de lecturas.

Herramientas de corrección de lecturas: Programas recomendados:
– Datos HiSeq: BLESS, Musket, RACER y SGA.
– Datos MiSeq: RACER.
– Datos humanos: Musket, RACER y SGA."
https://sourceforge.net/projects/musket/

Otras herramientas similares:
- ECHO （http://uc-echo.sourceforge.net/） Artículo http://genome.cshlp.org/content/21/7/1181.full
- CORAL （https://www.cs.helsinki.fi/u/lmsalmel/coral/） Literatura https://academic.oup.com/bioinformatics/article/27/11/1455/217071/Correcting-errors-in-short-reads-by-multiple
- Quake（http://www.cbcb.umd.edu/software/quake/index.html），Literatura http://genomebiology.biomedcentral.com/articles/10.1186/gb-2010-11-11-r116
- Cómo instalar Quake: https://www.plob.org/article/1635.html
- EC: un algoritmo de corrección de errores eficiente para lecturas cortas
- QuorUM: Un corrector de errores para lecturas Illumina.
  Para datos humanos, las mejores herramientas son más ligeras y la más reciente es bless. La antigua bless evaluada en el artículo no era muy buena.
  Literatura: https://academic.oup.com/bib/article/16/4/588/347932/Correcting-Illumina-data
  (La corrección de errores de lecturas generalmente se realiza después del trim.)

- Sprai（http://zombie.cb.k.u-tokyo.ac.jp/sprai/）Sprai (imorador de precisión de lecturas de un solo paso) es una herramienta para corregir errores de secuenciación en lecturas de un solo paso para el ensambaje *de novo*. Fue diseñado originalmente para corregir errores de secuenciación en lecturas de secuenciación de ADN de molécula única, especialmente en Lecturas Largas Continuas (CLRs) generadas por secuenciadores PacBio RS.


## 4. Ensamblaje de genomas (Assembly)

Estimación de K-mer:
- velvetK（http://www.vicbioinformatics.com/software.velvetk.shtml）：calcula el K-mer más adecuado
- KmerGenie（http://kmergenie.bx.psu.edu/）：estimaestima la mejor longitud de k-mer para el ensamblaje *de novo* del genoma.


Ensamblaje *de novo*:
- velvet（http://www.ebi.ac.uk/~zerbino/velvet/）：,适用于微生物基因组适用于 genomas microbianos
- VelvetOptimiser（http://www.vicbioinformatics.com/software.velvetoptimiser.shtml）：ensamblaje paraleloiple en lote con múltiples múltiples K-mers
- SPAdes（http://bioinf.spbau.ru/spades）：,适用于 Illumina、PacBio 数据（支持 gzip 压缩的 fastq 文件），同样适用于宏基因组。但实际情况，不太适用于病毒。适合 datos de Illumina y PacBio (soporta archivos fastq comprimidos en gzip), también se aplica a metagenómicaómica. En la práctica, no es muy adecuado para virus.
- Shovill（https://github.com/tseemann/shovill）：Ensamblaje más rápido de lecturas Illumina con SPAdes.
- Minia（https://github.com/GATB/minia）
- Soapdenovo（http://soap.genomics.org.cn/soapdenovo.html 或 https://github.com/aquaskyline/SOAPdenovo2）：desarrollado por BGI para ensambaje de genomas grandes
- ABySS（http://www.bcgsc.ca/platform/bioinfo/software/abyss）：basado en el algoritmo Grafo de De Bruijn, adecuado适用于大基因组适合 genomas grandes.
- ALLPATHS-LG（http://software.broadinstitute.org/allpaths-lg/blog/）：,适合于适合于组装 short reads 数据适合 el ensamblaje de datos de lecturas cortas
  Blog con instrucciones de uso de ALLPATHS-LG: http://blog.sciencenet.cn/blog-303373-717174.html
- <s>Celera Assembler（目前不再维护）（http://wgs-assembler.sourceforge.net/wiki/index.php?title=Main_Page），（https://sourceforge.net/projects/wgs-assembler/）：Illumina、454、Pacbio 等数据均适用。</s> <s>Celera Assembler (ya no se mantiene activamente) (http://wgs-assembler.sourceforge.net/wiki/index.php?title=Main_Page), (https://sourceforge.net/projects/wgs-assembler/): compatible con datos de Illumina, 454, Pacbio, etc.</s>
- CABOG（http://sourceforge.net/apps/mediawiki/wgs-assembler/index.php?title=Main_Page）：CABOG (Celera Assembler with Best Overlap Graph) es una extensión del software Celera Assembler. (Ya no se mantiene)
- Canu（http://canu.readthedocs.io/en/stable/#）：,适用于 PacBio RSII or Oxford Nanopore MinION 数据适合 datos de PacBio RSII u Oxford Nanopore MinION http://canu.readthedocs.io/en/latest/
- Platanus（http://platanus.bio.titech.ac.jp/?p=1）：,专门为高杂合基因组组装设计的软件，同样适用于 DNA Virus. software diseñado específicamente para el ensamblaje de genomas altamente heterocigotos, también es apto para virus de ADN.
- MetaPlatanus（http://platanus.bio.titech.ac.jp/?page_id=174）：Ensamblaje *de novo* y agrupamiento de secuencias de datos metagenómicos (ensamblaje metagenómico)
- RepARK（https://github.com/PhKoch/RepARK）：creación *de novo* de consensus de repeticiones a partir de lecturas NGS de genoma completo
- Literatura de RepARK: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4027187/
- Novoalign（http://www.novocraft.com/products/novoalign/）：mapeo de lecturas cortas en un genoma de referencia
- Falcon（https://github.com/PacificBiosciences/FALCON）：basado en el algoritmo String Graph, comúnmente utilizado para el ensamblador diploide de PacBio.
- GAGE（http://gage.cbcb.umd.edu/index.html）
- Arachne & AllPath（https://www.broadinstitute.org/scientific-community/software）
- Herramientas VISTA, incluyen AVID: （http://pipeline.lbl.gov/run5details.shtml）
- MIRA（https://sourceforge.net/p/mira-assembler/wiki/Home/）：un ensamblador de disparo de genoma completo y secuencias EST para datos Sanger, 454, Solexa (Illumina), IonTorrent y PacBio.
- gsAssembler/GS De Novo Assembler/runAssembly (basado en línea de comandos) y gsMapper (basado en línea de comandos)（http://www.454.com/products/analysis-software/）：ensamblaje para datos 454
- Newbler: es el algoritmo central de gsAssembler/GS De Novo Assembler, integrado en GS De Novo Assembler
- MetaVelvet（http://metavelvet.dna.bio.keio.ac.jp/）：un ensamblador de lecturas cortas para metagenómica
- MaSuRCA（ftp://ftp.genome.umd.edu/pub/MaSuRCA/）
  Cómo usar MaSuRCA para ensamblaje: https://www.plob.org/article/7853.html
- RAMPART（https://github.com/TGAC/RAMPART 或 http://www.earlham.ac.uk/rampart/）：un canalización para el ensamblaje *de novo* de datos de secuencia de ADN. 
- edena(http://www.genomic.ch/edena.php)
- cap3(http://seq.cs.iastate.edu/cap3.html)
- SHORTY（http://www3.cs.stonybrook.edu/~skiena/shorty/）：SHORTY se utiliza para ensamblar secuencias generadas por ABI SOLiD. Actualmente también se puede usar para datos de Illumina, pero primero se deben convertir a formato fasta.
- Links：http://www.bcgsc.ca/platform/bioinfo/software/links
- SGA：https://github.com/jts/sga

- iCORN2(http://icorn.sourceforge.net/)：corrige ensamblajes de PacBio de Bacterias y Eucariotas. 
- FaBox：http://users-birc.au.dk/biopv/php/fabox/：,an online fasta sequence toolbox，可转换格式、提取序列 una caja de herramientas en línea para secuencias fasta, permite convertir formatos y extraer secuencias.


Ensamblaje guiado por genoma de referencia:
- IDBA（http://i.cs.hku.hk/~alse/hkubrg/projects/idba_hybrid/index.html）
- Chromosomer（https://github.com/gtamazian/Chromosomer）
  Literatura de Chromosomer: https://link.springer.com/article/10.1186/s13742-016-0141-6
- Scaffold_Builder（https://sourceforge.net/projects/scaffold-b/）：Combinación de ensamblaje *de novo* y guiado por referencia con Scaffold_builder
  Literatura: http://scfbm.biomedcentral.com/articles/10.1186/1751-0473-8-23
- AlignGraph（https://github.com/baoe/AlignGraph）
- Ragout（https://github.com/fenderglass/Ragout）
- SyMap（http://www.agcol.arizona.edu/software/symap/）：un sistema de sintenia listo para usar con aplicación a genomas de plantas y genomas eucariotas.
- RACA（）
- AMOScmp（https://sourceforge.net/projects/amos/?source=directory）
- Medusa（https://github.com/combogenomics/medusa）
- CONTIGuator（http://contiguator.sourceforge.net/）
- Multi-CAR（http://140.114.85.168/Multi-CAR/index.php）
- refGuidedDeNovoAssembly_pipelines：https://bitbucket.org/HeidiLischer/refguideddenovoassembly_pipelines
  Referencia: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5681816/
  \# refGuidedDeNovoAssembly_pipelines es más adecuado para genomas grandes (eucariotas), requiere múltiples bibliotecas y bibliotecas pareja (bibliotecas de fragmentos grandes).

  

Ordenamiento de contigs contra una referencia:
- Mauve（http://darlinglab.org/mauve/mauve.html） Desde el menú de herramientas, seleccione 'Mover contigs'.
- ABACAS（http://abacas.sourceforge.net/index.html）
  Ejemplo:
  perl abacas.1.3.1.pl -r ../../ref_data/NC_022082.fasta -q ../genomes/NJXKYY22.genome.fasta -p "nucmer" -i 70 -c -m -b -o test_sorted.fasta
  Más instrucciones de uso: http://abacas.sourceforge.net/Manual.html

- GAP5（http://www.sanger.ac.uk/science/tools/gap5 或 https://sourceforge.net/projects/staden/）：Gap5 es un visualizador y herramienta herramientaeditor de ensamens de ensamedi/编辑工具. 
  Instrucciones de uso de GAP5: file:///C:/myProgram/Staden%20Package/share/doc/staden/manual/gap5_toc.html



Ensamblaje de virus (virus assembly):

- VirAmp（http://docs.viramp.com/en/latest/index.html）：una canalización de ensamblaje de genomas virales basada en Galaxy
  https://github.com/kdaily/viramp-project
  http://viramp.readthedocs.io/en/latest/
  Literatura de VirAmp: https://gigascience.biomedcentral.com/articles/10.1186/s13742-015-0060-y
- V-Fat（https://www.broadinstitute.org/viral-genomics/v-fat）：V-FAT es una herramienta para realizar el acabado computacional automatizado y la anotación de ensamblajes virales *de novo*. Herramienta de acabado, anotación y QA automatizada para ensamblajes virales.
- Viral-ngs（http://viral-ngs.readthedocs.io/en/latest/index.html）：,针对 rna 病毒 para virus de ARN
- IVA（https://github.com/sanger-pathogens/iva）：IVA es un ensamblador *de novo* diseñado para ensamblar genomas virales que no tienen secuencias repetidas, utilizando pares de lecturas Illumina secuenciados a partir de poblaciones mixtas con una profundidad extrema extremadamente alta y variable.
- VIGA（https://github.com/EGTortuero/viga）：VIGA un anotador sensible, preciso y automático de genomas virales *de novo*。


Otras herramientas relacionadas con virus:
(1) Detección de integración de virus
- BSVF（https://github.com/BioInfoTools/BSVF）：Bisulfite Sequencing Virus integration Finder
- VirusFinder （https://bioinfo.uth.edu/VirusFinder/）
- VirusSeq（http://odin.mdacc.tmc.edu/%7Exsu1/VirusSeq.html）：detedetecting known viruses and their integration sites in the human genome using next-generation sequencing data. 
- ViralFusionSeq (VFS)（https://sourceforge.net/projects/viralfusionseq/）：,discovering viral integration events and reconstructing fusion transcripts at single-base resolution.
- Vy-PER （http://www.ikmb.uni-kiel.de/vy-per/ ）：Detección de integración de virus mediante lecturas emparejadas (Paired End Reads)
- seeksv（https://github.com/qiukunlong/seeksv）：una herramienta precisa para la detección de variantesvariation estructural e integración de virus.
(2) Virus relacionados con datos metagenómicos
- VirMet（https://github.com/ozagordi/VirMet）：un conjunto de herramientas para metagenómica viral
- VirFinder（https://github.com/jessieren/VirFinder）：Paquete R para identificar secuencias virales de datos metagenómicos mediante firma de secuencia.
- METAVIR：http://metavir-meb.univ-bpclermont.fr/  METAVIR es un servidor web diseñado para anotar secuencias metagenómicas virales (lecturas crudas o contigs ensamblados).
- haploclique（https://github.com/armintoepfer/haploclique）：detección de SNP/indel de virus

- Kronos（http://kronos.readthedocs.io/en/latest/）：Un ensamblador de fljos de trabajo para anal e informática de genomas de cáncer.


Consulte http://www.mybiosoftware.com/assembly-tools para más herramientas de ensamblaje.


Los scaffold del borrador de genoma ensamblado requieren un cierre de huecos (gaps) posterior. El software con esta función incluye:
- SOAPdenovo GapCloser (http://sourceforge.net/projects/soapdenovo2/files/GapCloser/)
- IMAGE（https://sourceforge.net/projects/image2/）：Iterative Mapping and Assembly for Gap Elimination。
- GapFiller （https://www.baseclear.com/services/bioinformatics/basetools/gapfiller/）
  Blog con instrucciones de uso de GapFiller: https://www.plob.org/article/6182.html
- Otro另外一个  GapFiller（https://sourceforge.net/projects/gapfiller/）
- FinIS（https://sourceforge.net/projects/finis/）
- FGAP（https://sourceforge.net/projects/fgap/）：utiliza BLAST para alinear las secuencias de contigs al borrador del genoma, buscando la secuencia óptima que se superpone con el intervalo de hueco para cerrarlo.
  Literatura de FGAP: https://www.researchgate.net/publication/263207973_FGAP_An_automated_gap_closing_tool 或 http://bmcresnotes.biomedcentral.com/articles/10.1186/1756-0500-7-371
  Blog con instruccionesuso de FGAP: http://www.chenlianfu.com/?p=2333
- icorn（http://icorn.sourceforge.net/）：,that enables errors in the consensus sequence to be corrected by iteratively mapping reads to the current assembly. （corre校正序列）

Bandage：https://rrwick.github.io/Bandage/    Visualización de gráficos de ensamblaje

Software de procesos程流程 for bacterial comparative genomics: https://holtlab.net/2015/02/25/tools-for-bacterial-comparative-genomics/



Evaluación de errores del genoma

- REAPR (Recognition of Errors in Assemblies using Paired Reads) puede utilizar lecturas emparejadas para identificar errores en las secuencias genómicas. De esta manera, puede separar la secuencia del genoma en el hueco error o reemplazar la secuencia errónea con Ns. Además, realiza un recuento de información de errores.
  Sitio web oficial de REAPR: http://www.sanger.ac.uk/science/tools/reapr
  Para instalar REAPR, primero debe instalar los módulos R y Perl: File::Basename, File::Copy, File::Spec, File::Spec::Link, Getopt::Long, List::Util.
  Blog con uso de REAPR: http://www.chenlianfu.com/?p=2329

- QUAST（http://bioinf.spbau.ru/quast 或 http://quast.sourceforge.net/quast）：Herramienta de evaluación de calidad de ensamblaje de genomas
  Manual de QUAST: http://quast.bioinf.spbau.ru/manual.html
- LASTZ（http://www.bx.psu.edu/~rsharris/lastz/）
- Miller Lab：http://www.bx.psu.edu/miller_lab/
- Métricas de ensamblaje de Mauve - （http://code.google.com/p/ngopt/wiki/How_To_Score_Genome_Assemblies_with_Mauve）
- InGAP-SV - （http://ingap.sourceforge.net/）：InGAP también es útil para encontrar variantes estructurales entre genomas a partir de mapeos de lecturas.

merge-gbk-records：https://github.com/kblin/merge-gbk-records：Merge multiple GenBank records using a defined spacer sequence


Referencias de fljos de trabajo de ensamblaje: http://vlsci.github.io/lscc_docs/tutorials/assembly/assembly-protocol/#section-2-assembly
http://onlinelibrary.wiley.com/doi/10.1111/eva.12178/full
https://en.wikipedia.org/wiki/Sequence_assembly


## 5. Ensamblaje de EST
- iAssembler（http://bioinfo.bti.cornell.edu/tool/iAssembler/）：,利用MIRA以及CAP3软件，将454以及sanger测序产生的转录组数据(EST)拼接成contigs.
  Literatura relacionada: Yi Zheng, Liangjun Zhao, Junping Gao y Zhangjun Fei (2011) iAssembler: a package for de novo assembly of Roche-454/Sanger transcriptome sequences.


## 6. Alineamiento de secuencias
- BLAST+（ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/LATEST/）
- BLAT（http://genome.ucsc.edu/cgi-bin/hgBlat?command=start）
- clustalx/clustalw（http://www.clustal.org/）
  clustalX es la versión gráfica de clustalw, el primero se usa en Windows, el segundo en DOS.
  formato clustalw: http://web.mit.edu/meme_v4.9.0/doc/clustalw-format.html
  
  Más software: http://www.ebi.ac.uk/Tools/psa/
  
- MAFFT (Multiple Alignment using Fast Fourier Transform)（http://mafft.cbrc.jp/alignment/software/）
- MUSCLE (MUltiple Sequence Comparison by Log- Expectation)（http://www.drive5.com/muscle/）
- Mauve（http://darlinglab.org/mauve/mauve.html）
- Kalign（http://msa.sbc.su.se/cgi-bin/msa.cgi）
- T-Coffee（http://www.tcoffee.org/Projects/tcoffee/index.html）
- LAGAN & Shuffle-LAGAN（http://lagan.stanford.edu/lagan_web/index.shtml）
- MUGSY（http://mugsy.sourceforge.net）
- MUMmer（https://sourceforge.net/projects/mummer/）
- diamond（https://github.com/bbuchfink/diamond）
- amos（http://sourceforge.net/projects/amos/files/）：minimus2 es un componente del paquete de ensamblaje amos, su función es combinar合并两组 contig，延伸 contig 的长度，减少 contig 的数量. Amos es la sigla de A Modular, Open-Source whole genome assembler, dedicado a crear un sistema base para software de ensamblaje. minimus2 utiliza el algoritmo de detección de superposición nucmer, que es más rápido que el algoritmo de hash-overlap Smith-Waterman. Más información: http://amos.sourceforge.net/wiki/index.php/AMOS
- circlator（http://sanger-pathogens.github.io/circlator/）：Una herramienta para circularizar ensamblajes de genomas
- ACT (Artemis Comparison Tool)（http://www.sanger.ac.uk/science/tools/artemis-comparison-tool-act）
- GMAP（http://research-pub.gene.com/gmap/ 或 https://wiki.gacrc.uga.edu/wiki/Gmap-gsnap-Sapelo）：Un programa de mapeo y alineamiento genómico para secuencias de ARNm y EST
- MSA（https://www.ncbi.nlm.nih.gov/CBBresearch/Schaffer/msa.html）
  msa (http://www.bioconductor.org/packages/release/bioc/html/msa.html)：un paquete R para alineamiento múltiple de secuencias.
- MSAProbs（https://sourceforge.net/projects/msaprobs/ 或 http://msaprobs.sourceforge.net/homepage.htm#latest）
- PROBCONS（http://probcons.stanford.edu/index.html）
- Probalign（http://probalign.njit.edu/probalign/login）
- M-Coffee（http://www.tcoffee.org/Projects/mcoffee/）
- MergeAlign（http://www.stevekellylab.com/software/mergealign）

Comparación simple de Muscle, ClustalW y T-coffee: https://www.plob.org/article/4104.html
Más software de alineamiento: https://en.wikipedia.org/wiki/List_of_sequence_alignment_software
http://www.ebi.ac.uk/Tools/msa/


Formato de alineamiento múltiple de secuencias: http://www.cnblogs.com/tsingke/p/3940074.html
Enciclopedia de alineamiento múltiple de secuencias: https://en.wikipedia.org/wiki/Multiple_sequence_alignment
http://www.docin.com/p-812012331.html


Herramientas de alineamiento global
GASSST：http://www.irisa.fr/symbiose/projects/gassst/
Ejemplo:
Gassst -d tmp.fna -i gene_primer_out/Microcystis_aeruginosa.eryG_2.Microcystis_aeruginosa.eryG_2.p3_seqs.fa -o test.gassout -p 80 -m 8 -n 10


Conversión de alineamiento múltiple de proteínas a alineamiento de ácidos nucleicos:
pal2nal：http://www.bork.embl.de/pal2nal/


## 7. Alineadores de lecturas cortas (mapped)
- Bowtie（http://bowtie-bio.sourceforge.net/index.shtml）
- Bwa（http://bio-bwa.sourceforge.net）
- MAQ（http://maq.sourceforge.net/）
- subread（http://subread.sourceforge.net/）
- BBMap（https://sourceforge.net/projects/bbmap/）：Alineador de lecturas cortas BBMap y otras herramientas bioinformáticas. 
- BBtools（http://jgi.doe.gov/data-and-tools/bbtools/）
  Uso de BBmap: http://seqanswers.com/forums/showthread.php?t=58221 和 http://seqanswers.com/forums/showthread.php?t=44494
- Stampy（http://www.well.ox.ac.uk/project-stampy）：Rápido y sensible
  Literatura de Stampy: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3106326/
- samblaster: (https://github.com/GregoryFaust/samblaster) una herramienta para marcar duplicates y extraer lecturas discordantes y divididas de archivos sam.
- sambamba: (https://github.com/biod/sambamba 或 http://lomereiter.github.io/sambamba/) Herramientas para trabajar con datos SAM/BAM. (¡Recomendado!)
- ELAND
- Novoalign
- SMALT(http://www.sanger.ac.uk/science/tools/smalt-0 或 https://sourceforge.net/projects/smalt/)：SMALT alinea lecturas de secuenciación de ADN con secuencias de referencia genómicas. 
- BEDTools（https://code.google.com/p/bedtools/）


## 8. Llamada de SNPs/indels
- Dindel（http://sites.google.com/site/keesalbers/soft/dindel）：Detección de pequeñas inserciones/deleciones
- Pindel（http://gmt.genome.wustl.edu/packages/pindel/）：Detección de pequeñas inserciones/deleciones
- Samtools（http://samtools.sourceforge.net 或 http://www.htslib.org/）：Herramientas para el análisis de datos post-mapeo
- bamtools（https://github.com/pezmaster31/bamtools）
- GATK（https://software.broadinstitute.org/gatk/）
- bcftools（http://www.htslib.org/download/）
- VarScan（http://massgenomics.org/varscan 或 http://dkoboldt.github.io/varscan/）
- scalpel（https://sourceforge.net/projects/scalpel/?source=directory）：Descubrimiento de variantes genéticas y detección de indels
  Literatura de scalpel: http://www.nature.com/nmeth/journal/v11/n10/full/nmeth.3069.html
  Referencia de uso: http://www.bio-info-trainee.com/2341.html
- INDELseek（https://github.com/tommyau/indelseek）：Detección de indels
- ScanIndel（https://github.com/cauyrd/ScanIndel）
- Snippy（https://github.com/tseemann/snippy）：Llamada de SNPs e indels bacterianos
- Picard（http://broadinstitute.github.io/picard/ 或 https://github.com/broadinstitute/picard）：Programa Java
- SpeedSeq: (https://github.com/hall-lab/speedseq) desarrolladorollado por investigadores del Hospital General de Massachusetts y otras instituciones. Utiliza servidores de bajo costo y completa el mapeo, detección de variantes y anotación funcional de un genoma humano 50x en solo 13 horas. Esto resuelve el cuello de botella actual en bioinformática de WGS. Se aplica a datos de WGS, WES y secuenciación de paneles.
  Literatura de SpeedSeq: http://www.nature.com/nmeth/journal/v12/n10/full/nmeth.3505.html
  Consulte: http://www.biotrainee.com/thread-338-1-1.html
- Sequence Variant Analyzer（http://www.svaproject.org）：Muestra variantes en el contexto del genoma
- HugeSeq（https://github.com/StanfordBioinformatics/HugeSeq）：Canalización para variantes estructurales
  Consulte: http://blog.csdn.net/alex6plus7/article/details/50236375
- KvarQ（https://github.com/kvarq/kvarq）：Llamada directa y específica de variantes en lecturas FastQ de genomas bacterianos.

- nesoni: https://github.com/Victorian-Bioinformatics-Consortium/nesoni  un kit de herramientas para llamadacalling de SNPs de NGS / DGE de RNA-Seq / limpieza de lecturas.
- RedDog: https://github.com/katholt/RedDog  un pipeline de flujo de trabajo para análisis de secuencias de lectura corta, incluyendo la tarea de mapeo de lecturas, hasta la detección de variantes, seguida de análisis (solo SNPs).
  Los polimorfismos de nucleótido simple (SNPs) con puntu puntuación de calidad Phred ≥30 fueron identificados en cada aisl utilizando SAMTools.

## 9. SV, SNV
- LUMPY（https://github.com/arq5x/lumpy-sv）：un marco probabilístico general para el descubrimiento de variantes estructurales.
- MetaSV: (http://bioinform.github.io/metasv/) Un  llamada de variantes estructurales preciso e integrativo.
  Literatura de MetaSV: https://academic.oup.com/bioinformatics/article-lookup/doi/10.1093/bioinformatics/btv204
- FindSV: (https://github.com/dnil/FindSV)
- SomaticSniper（http://gmt.genome.wustl.edu/packages/somatic-sniper/ 或 https://github.com/genome/somatic-sniper）：Detección de SNV

FindTranslocations, CNVnator y fermikit

SV, CNV
- SV-Autopilot（https://github.com/ALLBio/allbiotc2）
- GASV：http://compbio.cs.brown.edu/projects/gasv/ 或 https://github.com/ZhihaoXie/GASV_
  Documento de GASV: https://vcru.wisc.edu/simonlab/bioinformatics/programs/gasv/GASV_UserGuide.pdf
- srGASV: https://github.com/dstorch/srGASV
- MultiBreak-SV: http://compbio.cs.brown.edu/projects/multibreaksv/ 或 https://github.com/raphael-group/multibreak-sv
- SVDetect: https://sourceforge.net/projects/svdetect/
- PEMer: detección de SV a partir de lecturas emparejadas. http://sv.gersteinlab.org/pemer/ 或 https://github.com/BIGLabHYU/PEMer
- VariationHunter: Una herramienta para identificar variantes estructurales a partir de datos WGS de lecturas emparejadas. https://sourceforge.net/projects/variationhunter/
- vaquita: https://github.com/seqan/vaquita  Identificación de variantes estructurales
  \# Nota: vaquita requiere que la secuencia de referencia tenga la extensión .fa.
- svmerge: https://sourceforge.net/projects/svmerge/ Una herramienta para el análisis de SV integrando llamadas de varios detectores de SV existentes.
- breakway: https://sourceforge.net/projects/breakway/  identificación de puntos de ruptura genómicos
- CNT-MD: Desconvolución de Mez de árboles de número de copias http://compbio.cs.brown.edu/projects/cnt-md/ 或 https://github.com/raphael-group/CNT-MD
- CNT-ILP: Árbol de número de copias http://compbio.cs.brown.edu/projects/cnt-ilp/ 或 https://github.com/raphael-group/CNT-ILP
- Canalización de análisis de Secuenciación del Exoma Completo： http://metamoodics.org/wiki/index.php?title=Whole_Exome_Sequencing_Analysis_Pipeline
- BSseeker2（https://github.com/BSSeeker/BSseeker2）：Una canalización versátil para datos de secuenciación bisulfito.

Más更多工具见：http://www.knowgene.com/question/8855
Herramientas relacionadas: https://omictools.com/indel-detection-category

- PopSV: https://github.com/jmonlong/PopSV  Detección de variantes de número de copias humanas

- Sniffles: https://github.com/fritzsedlazeck/Sniffles Sniffles es un detector de variantes estructurales que utiliza secuenciación de tercera generación (PacBio u Oxford Nanopore). 
- NGMLR: https://github.com/philres/ngmlr  NGMLR es un alineador de lecturas largas diseñado para alinear PacBio u Oxford Nanopore (estándar y ultra-largas) a un genoma de referencia con un enfoque en lecturas que abarcan variantes estructurales.

Revisión de software de variantes genéticas: https://academic.oup.com/bib/article/15/2/256/210976/A-survey-of-tools-for-variant-analysis-of-next
Algunas listas de software: http://seqanswers.com/forums/showthread.php?t=43


## 10. Chip-Seq		
- Findpeaks（http://vancouvershortr.sourceforge.net）

## 11. RNA-Seq		
- Cufflinks（http://cufflinks.cbcb.umd.edu）：Determina la abundancia de transcritos
- Tophat（http://ccb.jhu.edu/software/tophat/index.shtml）：Localización de puntos de corte (splicing)
- Trinity （https://github.com/trinityrnaseq/trinityrnaseq/wiki）
- Oases（http://www.ebi.ac.uk/~zerbino/oases/）：Ensamblaje basado en datos de transcriptoma
- Trans-ABySS（http://www.bcgsc.ca/platform/bioinfo/software/trans-abyss）：Ensamblaje de transcriptomas
- HISAT（http://ccb.jhu.edu/software/hisat/index.shtml）：Análisis de expresión diferencial de transcriptomas
- StringTie（http://ccb.jhu.edu/software/stringtie/）：Ensambla transcritos y estima los niveles de expresión
- Ballgown（https://github.com/alyssafrazee/ballgown）：Análisis de expresión diferencial de RNA-seq
  Lectura complementaria: Pasos detallados para realizar el análisis de expresión diferencial de transcriptomas usando tohat y Cufflinks
  Más software relacionadorna方面的软件：http://www.mybiosoftware.com/rna-analysis
  
  
## 12. Visores y editores de genomas
- Integrated Genome Browser（http://www.bioviz.org/igb/）
- Integrative Genomics Viewer（http://www.broadinstitute.org/software/igv/）
- Artemis（http://www.sanger.ac.uk/science/tools/artemis）
- CLC BioWorkbench（https://www.qiagenbioinformatics.com/products/clc-genomics-workbench/）
- Geneious（http://www.geneious.com/）http://www.geneious.com/features/assembly-mapping
- IGV （www.broadinstitute.org/igv/）


## 13. Graficación
- hemi（http://hemi.biocuckoo.org/index.php）：Dibujo gráfico de mapas de calor (heatmap)
- clusterProfiler: https://github.com/GuangchuangYu/clusterProfiler：Análisis estadístico y visualización de perfiles funcionales para genes y conjuntos de genes.


## 14. Gráficos circulares (Circos)
- circos（http://circos.ca）
- BioCircos：http://bioinfo.ibp.ac.cn/biocircos/index.php
- BRIG（http://brig.sourceforge.net/）
  Documento: http://brig.sourceforge.net/brig-tutorial-1-whole-genome-comparisons/
  https://sourceforge.net/projects/brig/files/
- OGDRAW（http://ogdraw.mpimp-golm.mpg.de/index.shtml）：Dibujo de gráficos circulares de genomas de orgánulos
- DNAPlotter（http://www.sanger.ac.uk/science/tools/dnaplotter）

## 15. Predicción de genes codificantes
- Glimmer（http://ccb.jhu.edu/software/glimmer/index.shtml）：Predicción de genes para bacterias, arqueas y virus
- GeneMarkS（http://topaz.gatech.edu/GeneMark/）：Predicción de genes para bacterias, arqueas, virus, fagos, virus y transcriptomas
- MetaGeneMark: Una herramienta de predicción de Genemark para metagenomas
- Prodigal（http://prodigal.ornl.gov/）：Predicción de genes para procariotas (alta GC), también aplicable a metaGenomas, pero no适用 para predicción de genes de ARN y genes virales.
- MetaGene Annotator（MetaGeneAnnotator）（http://metagene.cb.k.u-tokyo.ac.jp/）：un programa de búsqueda de genes para procariotas y fagos. También aplicable a metaGenomas.
- FragGeneScan（https://github.com/COL-IU/FragGeneScan.git）：Puede aplicarse para predecir genes procariotas en ensamblajes incompletos o genomas completos. 
- Orphelia（http://orphelia.gobics.de/）：Orphelia es una herramienta de búsqueda de ORF metagenómica para la predicción de genes codificantes de proteínas en secuencias de ADN ambiental cortas con origen filogenético desconocido.
- GenScan（http://genes.mit.edu/GENSCAN.html）：Herramienta de predicción de genes para vertebrados, Arabidopsis y maíz
- Pfam_Scan（http://pfam.xfam.org/）：Predicción de dominios de proteínas
  Herramienta PfamScan (ftp://ftp.ebi.ac.uk/pub/databases/Pfam/Tools/)
- tRNAscan-SE（http://lowelab.ucsc.edu/tRNAscan-SE/）：Predicción de tRNA
- ARAGORN：http://130.235.46.10/ARAGORN/ 或 http://mbio-serv2.mbioekol.lu.se/ARAGORN/Downloads/  ARAGORN detecta genes de tRNA, mtRNA y tmRNA.
- RNAmmer（http://www.cbs.dtu.dk/services/RNAmmer/）：Predicción de rRNA
- Barrnap（http://www.vicbioinformatics.com/software.barrnap.shtml 或 https://github.com/tseemann/barrnap）：Identificación de predicción de rRNA
- snoGPS（http://lowelab.ucsc.edu/snoGPS/）：Búsqueda de genes de snoRNA H/ACA en una secuencia genómica
- Snoscan（http://lowelab.ucsc.edu/snoscan/）：Búsqueda de genes de snoRNA guíaC/D box de metilación guide en una secuencia genómica

- OrfM: https://github.com/wwood/OrfM  predictor de ORF simple y rápido.
- getorf: http://emboss.sourceforge.net/apps/cvs/emboss/apps/getorf.html  Encuentra y extrae marcos de lectura abiertos (ORF).
- checktrans: http://emboss.open-bio.org/rel/rel6/apps/checktrans.html  Informa de codones de parada y estadísticas de ORF de una proteína.
- plotorf: http://emboss.sourceforge.net/apps/release/6.0/emboss/apps/plotorf.html  Grafica posibles marcos de lectura abiertos en una secuencia nucleotídica.
- ORFfinder: ftp://ftp.ncbi.nlm.nih.gov/genomes/TOOLS/ORFfinder/linux-i64/
  ORF Finder (herramienta en línea): http://www.bioinformatics.org/sms2/orf_find.html
- AntiFam: ftp://ftp.ebi.ac.uk/pub/databases/Pfam/AntiFam/  Identifica ORF falsos
  Artículo de AntiFam: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3308159/
  http://xfam.org/
  ¿ ejecutar AntiFam?
  hmmsearch --domtblout test_vs_antifam.out --tblout test_vs_antifam.out2 --domE 1e-10 --cpu 12 ../AntiFam.hmm test.faa

  
## 16. Software de flujos de trabajo (pipelines) de anotación
- Manatee（http://manatee.sourceforge.net/igs/index.shtml）：Manatee es una herramienta web para realizar anotaciones funcionales manuales.
- Ergatis（http://ergatis.sourceforge.net/index.html）、（https://sourceforge.net/projects/ergatis/）
- RAST（http://www.nmpdr.org/FIG/wiki/view.cgi/FIG/RapidAnnotationServer 或 http://rast.nmpdr.org/）：anotando genomas bacterianos y arqueales (en línea)
- prokka（http://www.vicbioinformatics.com/software.prokka.shtml）：Anotación para procariotas
- Annotationtools: https://github.com/rbotts/Annotationtools  Script Python para anotar secuencias desde un archivo fasta (Bacterial). Utiliza GeneMarkS y BioPython. (Para procariotas)

- RATT(Rapid Annotation Transfer Tool) http://ratt.sourceforge.net/：Anotación rápida de funciones génicas basada en genomas de referencia. RATT no forma parte actualmente de PAGIT.
- PAGIT（http://www.sanger.ac.uk/science/tools/pagit）（Post Assembly Genome Improvement Toolkit）. 


## 17. Estadísticas básicas post-ensamblaje
- assembly-stats（https://github.com/sanger-pathogens/assembly-stats）
- assembly-stats（https://github.com/rjchallis/assembly-stats）
- assemblyStatics（https://github.com/WenchaoLin/assemblyStatics）
- velvet-stats（https://github.com/ajmazurie/velvet-stats）
- gstawk（https://github.com/mspopgen/gstawk）
- seqStats(https://github.com/peteashton/seqStats): Se generan dos figuras: una contiene el histograma de distribución de longitudes y un gráfico de longitud acumulativa, la otra grafica el GC vs la longitud de la secuencia.

- TBtools(https://github.com/CJ-Chen/TBtools)


## 18. Análisis de K-mers y evaluación del tamaño genómico
- GCE（ftp://ftp.genomics.org.cn/pub/gce/）：Software utilizado por BGI para la evaluación de genomas
  Literatura de GCE: https://www.researchgate.net/publication/255722390_Estimation_of_genomic_characteristics_by_analyzing_k-mer_frequency_in_de_novo_genome_projects
  Blog con instrucciones de uso: https://www.plob.org/article/9388.html
- KmerGenie（http://kmergenie.bx.psu.edu/）
- Jellyfish （http://www.genome.umd.edu/jellyfish.html）
  Instrucciones de uso de Jellyfish: http://www.chenlianfu.com/?p=806
- KmerFreq


## 19. Software relacionado con el exoma
- Software para detección de CNV: CoNIFER（http://conifer.sourceforge.net/）
- Software de anotación de SNPs: annovar（http://annovar.openbioinformatics.org/en/latest/）


## 20. Anotación GO
- blast2go（https://www.blast2go.com/）
- GO_Annotation_Plot （https://github.com/ZhihaoXie/GO_Annotation_Plot.git）


## 21. Genómica comparativa
- Sibelia: A comparative genomics tool（http://bioinf.spbau.ru/en/sibelia）


## 22. Árboles filogenéticos
- Pairdist（https://github.com/frederic-mahe/pairdist）：Para construir árboles NJ
- TreeBest（https://github.com/lh3/treebest 或 http://treesoft.sourceforge.net/）
  Uso de TreeBest: http://blog.sina.com.cn/s/blog_620b35790100mcp6.html
- Fasttree（http://www.microbesonline.org/fasttree/）
- RAxML（https://sco.h-its.org/exelixis/web/software/raxml/index.html）：Herramienta para árboles ML
- PhyML（http://www.atgc-montpellier.fr/phyml/）：Herramienta en línea para construir árboles ML, también ejecutable localmente
- profileNJ（https://github.com/maclandrol/profileNJ）：Corrige校正 Gene tree 使用物种数和 NJ 树
- Figtree（http://tree.bio.ed.ac.uk/software/figtree/）：un visualizador gráfico de árboles filogenéticos y un programa para producir figuras listas para publicación.
- Dendroscope（http://dendroscope.org/）：Software para visualizar árboles filogenéticos y redes enraizadas.
- PATRIC（https://www.patricbrc.org/）：Constructor de árbolesboles Filogenéticos

- TempEst（http://tree.bio.ed.ac.uk/software/tempest/）TempEst es una herramienta para investigar la señal temporal y el "reloj" de las filogenias moleculares.

- liftover（http://hgdownload.cse.ucsc.edu/admin/exe/）：Conversión de coordenadas entre versiones del genoma (http://genome.ucsc.edu/)
  Consulte参考：http://www.plob.org/article/9541.html


- splign es una herramienta en NCBI para alinear cDNA con genoma, a través de splign se pueden encontrar fácilmente los exones de cada cDNA.
  Consulte: http://www.plob.org/article/7361.html

  
## 23. Metagenómica

(1) Herramientas de ensamblaje metagenómico

Herramientas de ensamblaje disponibles: SOAPdenovo, SPAdes, IDBA, MetaPlatanus, ABySS, CABOG
- TruSPAdes（http://cab.spbu.ru/software/spades/）：,用于宏基因组的拼接 para el ensamblaje metagenómico
- MEGAHIT（https://github.com/voutcn/megahit）
- Ray（https://github.com/sebhtml/ray 或 http://denovoassembler.sourceforge.net/）：un ensamblador *de novo* que utiliza MPI 2.2. Ray Meta: ensambaje metagenómico escalable y perfilado.
- Meraga（）
- Minia （http://minia.genouest.org/）
- MetaVelvet（http://metavelvet.dna.bio.keio.ac.jp/）：un ensamblador de lecturas cortas para metagenómica
  Consulte: http://blog.sina.com.cn/s/blog_670445240101lg2a.html
- MetAMOS（https://github.com/marbl/metAMOS）：Un canal de ensamblaje y análisis metagenómico y de aisl construido con AMOS.
- Subtractive Assembly（https://sourceforge.net/projects/subtractive-assembly/）：Compara diferencias entre metagenomas mediante ensamblaje. El objetivo principal es reducir el costo del ensamblaje metagenómico, centrándose en descubrir especies y genes diferenciales. Primero selecciona lecturas con k-mers diferenciales basándose en las lecturas originales, y luego ensambla las lecturas seleccionadas.
  Consulte: http://blog.sina.com.cn/s/blog_83f77c940102vvwr.html

(2) Otros

- MG-RAST（http://metagenomics.anl.gov/） http://evomics.org/learning/genomics/metagenomics/mg-rast/
- GOTTCHA（https://github.com/LANL-Bioinformatics/GOTTCHA）
- MIDAS（https://github.com/snayfach/MIDAS）：Metagenomic Intra-Species Diversity Analysis System. Nuestra base de datos de referencia de especies bacterianas y recursos de datos genómicos asociados están disponibles en http://lighthouse.ucsf.edu/MIDAS。
  Literatura de MIDAS: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5088602/
- checkM（https://github.com/Ecogenomics/CheckM）

(3) Clasificación taxonómica de especies
- Kraken（http://ccb.jhu.edu/software/kraken/）
- Kaiju（http://kaiju.binf.ku.dk/ 或 https://github.com/bioinformatics-centre/kaiju）：Kaiju es un programa para la clasificación taxonómica sensible de lecturas de secuenciación de alto rendimiento de experimentos de metogenómicaómica de genoma entero completo o metatranscriptómica.
- sourmash （pip install -U https://github.com/dib-lab/sourmash/archive/master.zip）
- MetaPhlAn2（http://segatalab.cibio.unitn.it/tools/metaphlan2/ 或 https://bitbucket.org/biobakery/metaphlan2/src/default/）
- mOTU（http://www.bork.embl.de/software/mOTU/）
- PanPhlAn（http://segatalab.cibio.unitn.it/tools/panphlan/）
- ConStrains（https://bitbucket.org/luo-chengwei/constrains）：,reads 数据作为输入
  Literatura: http://www.nature.com/nbt/journal/v33/n10/full/nbt.3319.html
- Krona（https://github.com/marbl/Krona/wiki）：Visualización de taxonomía

(4) Binning
- metaBAT：https://bitbucket.org/berkeleylab/metabat
- ESOM：http://databionic-esom.sourceforge.net/
- ESOM：https://sourceforge.net/projects/databionic-esom/?source=directory
- CheckM：http://ecogenomics.github.io/CheckM/ 或 https://github.com/Ecogenomics/CheckM/releases
- MetaCluster：http://i.cs.hku.hk/~alse/MetaCluster/
- MetaBin：http://metabin.riken.jp/


(5) Otras herramientas
- tetramerFreqs/Binning: https://github.com/tetramerFreqs/Binning
- Hawth's Analysis Tools for ArcGIS: http://www.spatialecology.com/htools/overview.php

Otro:
http://www.360doc.com/content/16/0815/17/35684706_583419969.shtml


Introducción a las bases de datos comunes en la investigación de ecología microbiana: http://www.cnblogs.com/nkwy2012/p/6396435.html


Referencia:
http://msb.embopress.org/content/9/1/666 (un artículo de revisión)
http://www.ebiotrade.com/newsf/2014-8/2014814163301250.htm


TaxonKit: https://bioinf.shenwei.me/taxonkit/  Efficient NCBI Taxonomy Toolkit


## 24. 16S Diversidad microbiana
- UNBIAS
- Vseach
- usearch
- NINJA

- SRA Toolkit: https://trace.ncbi.nlm.nih.gov/Traces/sra/sra.cgi?cmd=show&f=software&m=software&s=software
  http://ncbi.github.io/sra-tools/
  https://github.com/ncbi/sra-tools
  Cómo convertir el formato SRA a formato FastQ (fq) con fastq-dump: http://www.cnblogs.com/emanlee/archive/2013/04/15/3022328.html

  
## 25. Predicción de familias de genes
- GFam（http://www.paccanarolab.org/gfam）：GFam es una herramienta de línea de commands para la anotación automática de familias de genes.


## 26. Transcritos de longitud completa
- SQANTI（https://bitbucket.org/ConesaLab/sqanti）：Herramienta de descubación para el descubrimiento de nuevas estructuras de transcritos de secuenciación de transcriptoma de longitud completa
  http://www.ngsgo.com/biology/1436.html

  
## 27. Anotación COG
- eggNOG-mapper（http://eggnogdb.embl.de/#/app/emapper）

Referencia: http://diyitui.com/content-1466484195.47288872.html


- ASpipe（https://sourceforge.net/projects/aspipe/）：ASpipe es un canal para procesar alineamientos GeneSeqer/GMAP e identificar eventos de empalme alternativo (AS) a partir de los alineamientos. Requiere unix bash, perl 5.0+ con módulo DBI y MySQL5.0+ para ejecutarse correctamente.

## 28. Navegadores de genomas
- UCSC Genome Browser
  http://genome.ucsc.edu

- Ensembl Genome Browser
  http://www.ensembl.org

- NCBI Genome Browser
  http://www.ncbi.nlm.nih.gov/mapview

- GMOD GBrowser
  http://gmod.org

- UTGB
  http://utgenome.org/

- IGV (Broad)
  http://www.broadinstitute.org/igv/

- JBrowser (javascript)
  http://jbrowse.org/

- Argo Genome Browser (Broad)
 http://www.broadinstitute.org/annotation/argo/

- DNAnexus
  https://dnanexus.com/genomes/hg18/public_browse

- Gaggle Genome Browser
  http://gaggle.systemsbiology.net/docs/geese/genomebrowser/

- Celera Genome Browser
  http://sourceforge.net/projects/celeragb/files/

- Apollo Genome Annotation Curation Tool
  http://apollo.berkeleybop.org/current/index.html

  

Referencia: http://www.dxy.cn/bbs/thread/1385361#1385361
Guía de uso del visor de mapas: http://www.dxy.cn/bbs/thread/1385361#1385361


NCBI utiliza números de versión como build 36; UCSC, etc. utilizan números como hg18, hg19 para el genoma humano; Ensembl tiene sus propias versiones de lanzamiento, pero los datos utilizan la nomenclatura de NCBI.
Los números de versión de ambos estilos tienen relación, por ejemplo, genoma humano: hg19 = GRCh37, o la versión de parche Build 38 release 7 corresponde a GRCh38.p7.


Otras herramientas:
- HUMAnN2（https://bitbucket.org/biobakery/humann2/wiki/Home）：


## 29. Análisis de pan-genomas
- Roary（http://sanger-pathogens.github.io/Roary/）：análisis de pan-genomas procariotas a gran escala y rápido
  Literatura de Roary: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4817141/
- BPGA（http://www.iicb.res.in/bpga/index.html 或 https://sourceforge.net/projects/bpgatool/）
  BPGA es un paquete de software ultra rápido que proporciona un análisis integral de pan-genomas de microorganismos. (Solo para procariotas)
  Literatura de BPGA: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4829868/pdf/srep24373.pdf
- PanGP （https://pangp.ybzhao.com/）PanGP es una herramienta para analizar rápidamente el perfil de pan-genoma bacteriano. (Análisis y curva曲线 de características del pan-genoma)
- panOCT（https://sourceforge.net/projects/panoct/?source=directory）
  Literatura de panOCT: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3526259/
- LS-BSR（https://github.com/jasonsahl/LS-BSR）
- BSR（http://bsr.igs.umaryland.edu/）
  Literatura de LS-BSR: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3976120/
- PGAP: Canal de análisis de pan-genomas. (Software automatizado para análisis de pan-genómica procariota)
  https://github.com/kastman/pgap-docker
  https://sourceforge.net/projects/pgap/
  Literatura de PGAP: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3268234/
  \# ¡PGAP es muy lento! ¡Úsalo con precaución!
- metaPGAP（https://github.com/mitul-patel/metaPGAP）：Metagenomic Pan Genome Analysis Pipeline 
- AGAPE（https://github.com/yeastgenome/AGAPE）：Análisis de pan-genomas para levaduras

- Parsnp（http://harvest.readthedocs.io/en/latest/content/parsnp.html 或 https://github.com/marbl/parsnp） Alineamiento múltiple rápido del genoma central. (genomas bacterianos)
  Artículo de Parsnp: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4262987/

- PGAP-X: https://pgapx.ybzhao.com/  PGAP-X es una plataforma de análisis genómico comparativo microbiano con interfaz gráfica. (Interfaz gráfica para análisis de genómica comparativa)


## 30. Transposones
- LTR_retriever（https://github.com/oushujun/LTR_retriever）：Identificación de retrotransposones LTR


## 31. Genes de resistencia y factores de virulencia
Herramientas:
- abricate（https://github.com/tseemann/abricate）：Cribado masivo de contigs para genes de resistencia抗抗菌和 virulencia genes
- ARIBA: https://github.com/sanger-pathogens/ariba  Detección de genes de resistencia (lecturas fastq como entrada)
- SRST2: https://github.com/katholt/srst2 或 http://katholt.github.io/srst2/
- c-SSTAR: https://github.com/chrisgulvik/c-SSTAR
- ARGs-OAP: https://github.com/biofuture/Ublastx_stageone 和 http://smile.hku.hk/SARGs
  Literatura de ARGs-OAP: https://academic.oup.com/bioinformatics/article/32/15/2346/1743463
  \# Nota: el archivo de entrada de ARGs-OAP es fastq

- Meta-MARC: https://github.com/lakinsm/meta-marc  Detección de genes de resistencia a antibióticos en metagenomas
- DeepARG: http://bench.cs.vt.edu/deeparg  Un método de aprendizaje profundo para predecir genes de resistencia a antibióticos a partir de datos metagenómicos.
  Literatura de DeepARG: https://microbiomejournal.biomedcentral.com/articles/10.1186/s40168-018-0401-z

  

Base de datos de genes de resistencia a antibióticos:
- ARDB: http://ardb.cbcb.umd.edu/index.html
- BacMet （http://bacmet.biomedicine.gu.se/）: Antibacterial biocide and metal resistance genes database
  \# BacMet tiene herramientas配套检索注释工具，其执行如：
   perl /sdg/database/BacMet_v1.1/BacMet-Scan_v1.1.pl -i ./final.scaffold.fa -o E6.3 -d /sdg/database/BacMet_v1.1/BacMet_EXP.704 -blast -e 0.00001 -cpu 10 -columns all -p 20 -table -report -counts -v
- CARD: https://card.mcmaster.ca/
- Resfams: http://www.dantaslab.org/resfams
- NCBI Bacterial Antimicrobial Resistance Reference Gene Database: https://www.ncbi.nlm.nih.gov/bioproject/PRJNA313047
- ARG-ANNOT: http://en.mediterranee-infection.com/article.php?laref=283%26titre=arg-annot
- ResFinder: https://cge.cbs.dtu.dk/services/ResFinder/ ResFinder identifies acquired antimicrobial resistance genes and/or find chromosomal mutations in total or partial sequenced isolates of bacteria.
  ResFinder: https://bitbucket.org/genomicepidemiology/resfinder
- EcOH: https://github.com/katholt/srst2/tree/master/data


## 32. Detección de secuencias de plásmidos
- PlasmidFinder: https://cge.cbs.dtu.dk/services/PlasmidFinder/   PlasmidFinder identifies plasmids in total or partial sequenced isolates of bacteria. PlasmidFinder, which searches for matches in a replicon database, had the highest precision (1.0) but was restricted by the contents of its database and the contig length obtained from de novo assembly (recall = 0.33).
  Enlace de descarga de la base de datos PlasmidFinder: https://cge.cbs.dtu.dk//services/data.php
- cBAR（http://csbl.bmb.uga.edu/~ffzhou/cBar/） recall and precision of 0.77 and 0.63.
- Recycler（https://github.com/Shamir-Lab/Recycler） It correctly predicted small plasmids but failed with long plasmids (recall = 0.12, precision = 0.28).
- PlasmidSPAdes（http://spades.bioinf.spbau.ru/plasmidSPAdes/）
- PLACNET（https://sourceforge.net/projects/placnet/）
- PLACNET2FASTA（https://github.com/tomdeman-bio/PLACNET2FASTA）：Converts PLACNET output to a FASTA file containing plasmid contigs 


## 33. Microorganismos
- Nullarbor: https://github.com/tseemann/nullarbor  Pipeline to generate complete public health microbiology reports from sequenced isolates.


## 34.
Genome-to-Genome Distance Calculator (GGDC): http://ggdc.dsmz.de/distcalc2.php  Calcula el valor de hibridación ADN-ADN (DDH).


## 35.
- MinCED: https://github.com/ctSkennerton/minced Detección de CRISPRs
- CRT: http://www.room220.com/crt/  CRISPR Recognition Tool

## 36.
- Piggy（https://github.com/harry-thorpe/piggy）：Pipeline for analysing intergenic regions in bacteria

## 37. IS
- ISMapper（https://github.com/jhawkey/IS_mapper）ISMapper finds locations of an IS query in short read data using a series of mapping steps.

## 38.
- ncbi-genome-download（https://github.com/kblin/ncbi-genome-download）：Scripts to download genomes from the NCBI FTP servers。
  Ejemplo:
   ~/.pyenv/versions/3.5.2/bin/ncbi-genome-download -F fasta -g Vibrio -o Vibrio_genomes -p 16 -r 15 bacteria

   
## 39. Diseño de cebadores
- PrimerMapper: https://github.com/dohalloran/PrimerMapper
- primer3（https://github.com/primer3-org/primer3）
- PrimerView（https://github.com/dohalloran/PrimerView）


## 40.
- Herramientas para el análisis de anotación de funciones de proteínas: https://classes.soe.ucsc.edu/bme225/Fall07/BME225.serverlist.html
  https://classes.soe.ucsc.edu/bme225/Fall08/BME225.serverlist08.html

  
## 41.
- GWDSR: https://github.com/tigerxu/GWDSR

- COV2HTML: https://mmonot.eu/COV2HTML/connexion.php  A Visualization and Analysis Tool of Bacterial Next Generation Sequencing (NGS) Data.


## 42. Metilación
- Bismark（https://www.bioinformatics.babraham.ac.uk/projects/bismark/）：A tool to map bisulfite converted sequence reads and determine cytosine methylation states. (Identificación de metilación)

- seqtools: http://www.sanger.ac.uk/science/tools/seqtools The SeqTools package contains three tools for visualising sequence alignments: Blixem, Dotter and Belvu.


## 43. Factores de transposición
- CLARI-TE: https://github.com/jdaron/CLARI-TE Predicts Transposable Elements (TEs) in complexe genome such as wheat（小麦）.


## 44. Análisis de secuencias repetidas
- TRF: http://tandem.bu.edu/trf/trf.download.html
- Msatfinder: http://www.bioinformatics.org/project/?group_id=469  https://github.com/knirirr/Msatfinder  Msatfinder es un script Perl simple que detecta repeticiones de microsatélites perfectos (1-6 pb) en secuencias de ácidos nucleicos o proteínas.
- MISA - MIcroSAtellite identification tool: http://pgrc.ipk-gatersleben.de/misa/
- msatcommander: http://www.softpedia.com/get/Science-CAD/msatcommander.shtml （Plataforma Windows）


Expansión:

(1) Tipificación de SSR/STR

La solución解决方法如下：

1. 首先确定研究的物种是什么？有很多物种是已经有文献发表的SSR序列，同时又对应的引物序列供参考。这种的比较简单，不用自己设计引物。但尽量选择文献报道，比较多的多态性好的位点。比如：大豆的SSR位点，对应的引物序列也有，但文献一般发表的位点有哪些，哪些位点做了很多研究，多态性比较好，尽量选择这样的位点。

2. 所研究的物种，没有文献报道。这样的话，比较麻烦，需要自己开发SSR引物。首先，你要从该物种的基因组序列中，筛选STR位点。具体方法有很多，比较：富集文库的方法，SSR-Hunter软件，等，有很多SSR引物开发的方法和资料。从基因组序列上选择来讲，尽量选择不连锁的位点。筛选出重复序列的位点后，要对位点的多态性检测。最终筛出的位点：不连锁、多态性好、易扩增。

3. ABI3730上，最终上机是检测荧光信号，引物5‘端荧光标记，这个检测量和速度很快，成本高，只有筛好引物，后续批量实验时，再上机。前期引物筛选，还是用普通引物（不带标记），跑PAGE胶，取20个左右样本，大概看下扩增片段，多态性，即可。

首先你要有序列，不知你做的是什么物种。把这些序列输入到在线的：http://www.genomics.ceh.ac.uk/cgi-bin/msatfinder/msatfinder.cgi 网站中，确定微卫星所在的位置；然后在微卫星序列两翼设计引物。


## 45. Visores
- SnapGene: http://www.snapgene.com/products/file_compatibility/GenBank/


## 46. Herramientas Pfam
- Pfam_Scan（http://pfam.xfam.org/）：Predicción de dominios de proteínas
- Herramienta PfamScan (ftp://ftp.ebi.ac.uk/pub/databases/Pfam/Tools/)
- InterProscan web oficial: 
  http://www.ebi.ac.uk/interpro/
  http://www.ebi.ac.uk/interpro/interproscan.html

- AntiFam: ftp://ftp.ebi.ac.uk/pub/databases/Pfam/AntiFam/  Identifica ORF falsos
  Artículo de AntiFam: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3308159/
  http://xfam.org/
  Cómo ejecutar AntiFam?
  hmmsearch --domtblout test_vs_antifam.out --tblout test_vs_antifam.out2 --domE 1e-10 --cpu 12 ../AntiFam.hmm test.faa

- wKinMut-2: http://kinmut2.bioinfo.cnio.es/KinMut2  wKinMut-2 es un marco integrado para el análisis e interpretación de las consecuencias de variantes en el cinoma humano.
- GOTaxExplorer: http://gotax.bioinf.mpi-inf.mpg.de/  GOTaxExplorer presents a new approach to comparative genomics that integrates functional information and families with the taxonomic classification.


## 47. Otras herramientas
- PathSeq: Use PathSeq para la identificación de contaminación entre especies
  https://software.broadinstitute.org/gatk/blog?id=23205
  ftp://ftp.broadinstitute.org/bundle/pathseq/


## 48. Análisis de estructura génica
- GSDS: http://gsds.cbi.pku.edu.cn/


## 49. Bases de datos
Base de datos de Drosophila: http://flybase.org/

Base de datos de levaduras: https://www.yeastgenome.org/

Descarga de datos de levaduras: https://www.yeastgenome.org/download-data


## 50. Notas adicionales (Pequeños consejos)
Software de ensamblaje de genomas adecuado para datos de NGS
1. ALLPATHS-LG
2. Velvet
3. SOAPdenovo
4. Bambus2
5. CABOG
6. MSR-CA
7. SGA
8. VCAKE
9. SHARCGS
10. SSAKE
11. Euler

Software de ensamblaje de genomas adecuado para datos de Sanger
1. Newbler
2. Celera
3. CABOG
4. Edena
5. Shorty

Algoritmos de ensamblaje:

A) Métodos de superposición/diseño/consenso (OLC) (se basan en un grafo de superposición)

Software: CABOG, Newbler, Shorty, Edena

B) Métodos de Grafo de De Bruijn (DBG) (utilizan alguna forma de grafo K-mer)

Software: SOAPdenovo, Euler, Velvet

C) Algoritmos de grafo greedy (utilizan OLC o DBG)

Software: SSAKE, SHARCGS, VCAKE



## 51. Búsqueda y descarga de literatura

(1) Library Genesis
1. http://gen.lib.rus.ec (La velocidad de este sitio web es bastante rápida)
2. http://libgen.io (La velocidad de este sitio web es lenta 较慢)
3. http://libgen.io/scimag/ (Este sitio web se utiliza principalmente para buscar artículos)

(2) Sci-hub
- http://tool.yovisun.com/scihub/
- http://sci-hub.tw/
- https://sci-hub.shop/
- https://sci-hub.org.cn/

(3) BGPT MCP
- https://github.com/connerlambden/bgpt-mcp : BGPT API - REST/Python y MCP búsqueda de artículos científicos que devuelve evidencia experimental estructurada, limitaciones, conflictos de interés y campos de disponibilidad de datos/código. Servidor MCP para buscar artículos científicos con datos experimentales de texto completo. Admite puntos finales SSE y HTTP transferible.
