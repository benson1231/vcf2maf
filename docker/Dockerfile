FROM continuumio/miniconda3:latest

# 建立工作目錄
WORKDIR /opt/vep

# 複製 conda 環境 YAML 檔
COPY vcf2maf_env.yaml .

# 建立 Conda 環境（名稱為 vep）
RUN conda env create -f vcf2maf_env.yaml

# 啟用 conda 環境
SHELL ["conda", "run", "-n", "vep", "/bin/bash", "-c"]

# 設定預設進入環境
RUN echo "conda activate vep" >> ~/.bashrc

# VEP data cache 與 fasta 建議 volume mount 外部掛載
VOLUME ["/data", "/root/.vep"]

# 預設執行 shell
CMD ["/bin/bash"]
