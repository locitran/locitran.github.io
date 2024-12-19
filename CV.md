---
layout: default
title: CV
nav_exclude: true
permalink: /cv/
---

<div style="display: flex; justify-content: space-between; align-items: center;">
  <div>
    <strong>Name</strong>: <strong>Tran</strong> Dinh Quang Loc (Loci) <br>
    <strong>Birth Year</strong>: 1998 <br>
    <strong>Birth Place</strong>: Vietnam <br>
  </div>
  <div>
    {% for file in site.static_files %}
      {% if file.path contains 'photo.jpg' %}
        <img src="{{file.path}}" alt="Loc's Photo" style="width: 150px; height: auto;">
      {% endif %}
    {% endfor %}
  </div>
</div>

## Experience
---
- **National Tsing Hua University**
    - **Graduate Research Assistant**, Sep 2024 - Present <br>
    **Skills**: Large Language Models (LLMs), Drug Design <br>
    <br>
    - **Master Student**, Sep 2022 - Sep 2024 <br>
    **Thesis title**: TANDEM-DIMPLE: Transfer-leArNing-ready and Dynamics-Empowered Model for DIsease-specific Missense Pathogenicity Level Estimation <br>
    **Advisor**: [Dr. Lee-Wei Yang](https://dyn.life.nthu.edu.tw/main/) <br>
    **Skills**: Structural Computational Biology and Machine Learning/AI (DNN) <br>
    <br>

- **Khoa Thuong Biotechnology Company**
    - **R&D Staff**, May 2021 - Jun 2022 <br>
    **Skills**: qRT-PCR and Bioinformatics <br>

- **HCM University of Science**
    - **Undergraduate Student**, Sep 2016 - Aug 2020 <br>
    **Thesis title**: Improved fermentation efficiency for rhPDGF-BB production by methanol pulse method <br>
    **Advisor**: Dr. Tri-Nhan Nguyen <br>
    **Skills**: Protein Assays <br>

## Education
---
- **M.S. in Bioinformatics and Structural Biology**, National Tsing Hua University, 2024
- **B.S. in Biotechnology**, HCM University of Science, 2020

## Publications
---
- [**Production of rhPDGF-BB from Pichia pastoris in 7.5-L and 25-L fermentation scales**](https://huib.hueuni.edu.vn/wp-content/uploads/2020/12/457-462.pdf), Vietnam National Conference on Biotechnology, 2020

## Languages
---
- **Programming Languages**: Python (70%), Matlab (25%), Bash (5%)
- **Web Development**: HTML, Ruby, CSS (Minor)
- **Human Languages**: Vietnamese (Native), English (Fluent), Chinese (Basic)

