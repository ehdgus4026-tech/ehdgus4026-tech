# 이동현 | Server & Infrastructure Engineer

서버·인프라 엔지니어를 목표로 Linux, VMware 가상화, 네트워크와 공유 스토리지를 학습하고 있습니다.
팀 프로젝트에서 직접 서버를 구축하고, 로그와 설정을 대조하여 장애 원인을 분석하며, 작업 과정과 검증 결과를 문서화하고 있습니다.

## Tech Stack

| 구분 | 프로젝트에서 사용한 기술 |
| --- | --- |
| Server / OS | Ubuntu, Rocky Linux, Nginx |
| Virtualization | VMware Workstation, VMware ESXi, vCenter |
| Storage | Ceph, CephFS, NFS-Ganesha, LVM |
| Network / Security | VyOS, FRR, VLAN, NAT, Netplan, iptables, Sophos UTM |
| Database / Data | MySQL, Python, 공공데이터 Open API |
| Deployment / Tools | Docker, Git / GitHub, Cisco Packet Tracer, Wireshark |

## Projects

### 1차 | 공공데이터 API를 이용한 재난별 대피소 플랫폼

**2026.08.18 ~ 2026.09.03 · 완료**

공공데이터 API를 활용하여 사용자용 대피소 조회 서비스와 관리자용 데이터 관리 서비스를 분리한 팀 프로젝트입니다.

**담당 역할**
- 프로젝트 진행 총괄 및 VMware Workstation·VyOS 기반 서버·네트워크 인프라 구성
- 서버 역할에 따른 서브넷 분리와 라우팅 설정, Nginx 서버 구성 및 관리자 서버의 IP 접근 제어
- Python 기반 Open API 데이터 수집과 MySQL DB·테이블 설계
- 인프라 토폴로지와 구축·검증 과정 문서화, 최종 보고서 작성 총괄 및 인프라 파트 발표

**문제 해결 경험**
- API 요청 건수 제한을 확인하고 약 3,000건의 데이터를 1,000건 단위로 나누어 순차 수집하도록 수정
- VMnet·네트워크 어댑터 연결을 점검하고 서브넷·라우팅 구성을 재정리하여 서버 간 통신 복구
- 배포 중 최신 코드가 반영되지 않는 문제를 팀원과 분석하고, Maven 재빌드 후 Docker 컨테이너에 반영하여 해결

[Admin Server](https://github.com/ehdgus4026-tech/admin) · [Service Server](https://github.com/ehdgus4026-tech/servic)

### 2차 | VMware 기반 가상화 및 Ceph 공유 스토리지 인프라 구축

**진행 중 · 2026년 11월 기준**

물리 서버 3대의 ESXi 환경을 vCenter로 관리하고, CephFS·NFS-Ganesha 기반 공유 스토리지에 vCenter와 업무용 VM을 배치하는 팀 프로젝트입니다.

**담당 역할 및 구축 내용**
- ESXi·vCenter 가상화 환경 구성과 vSwitch·포트 그룹·VMkernel 네트워크 설정
- Ubuntu 3노드 CephFS 구성 및 NFS-Ganesha를 통한 ESXi 3대의 NFS 4.1 공유 데이터스토어 연결
- vCenter VM의 로컬 데이터스토어에서 공유 스토리지로 저장 위치 이전
- Ubuntu01 가상 디스크의 씩→씬 전환 및 3개 노드 OSD의 각각 270GiB 확장
- Ubuntu 템플릿 제작·VM 배포, Kea DHCP 자동 할당 검증 및 MySQL 설치·구동 확인
- Sophos UTM의 VLAN·NAT·방화벽 규칙 설정과 업무망 접근 제어 구조 검토

**문제 해결 경험**
- VMkernel의 vSwitch 연결 위치와 정적 경로를 수정하여 ESXi의 NFS 접근 복구
- Docker 관련 iptables 전달 정책을 분석하고 필요한 전달 규칙을 추가하여 경유 통신 복구
- Ceph MON의 실제 적용 네트워크 범위를 수정하고 클러스터 HEALTH_OK 확인
- DB VM의 initramfs·GRUB를 재생성하여 부팅 복구

> UTM 업무망의 통신 검증과 접근 제어 설계 변경은 진행 중입니다.

[CephFS 구축 기록](https://app.notion.com/p/405cad60670581b2b060d31245f614bb) · [NFS 연동·vCenter 이전](https://app.notion.com/p/407cad606705811880d7e479511bba17) · [VM 배포·OSD 확장](https://app.notion.com/p/408cad60670581288403ff34e5dc643b)

## Certifications

- CCNA · 2024.08
- 리눅스마스터 2급 · 2025.03
- 네트워크관리사 2급 · 2026.08

## Portfolio

서버 구축, 네트워크 설정, 서비스 연동과 트러블슈팅 과정을 Notion에 기록하고 있습니다.

[Server Engineer Portfolio](https://app.notion.com/p/3dbcad60670580549c42c35699ccd971)
