<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>팀 활동 대시보드</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;500;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Calm Focus -->
    <!-- Application Structure Plan: The application is designed as a dashboard to provide a quick overview and detailed tracking capabilities. It's structured into two main sections: 1) An "Events" section with a chart to visually summarize the progress of key team activities like the 'Machine Learning Track', making it easy to grasp overall progress. 2) A "Team Attendance" section with an interactive grid, which is a more user-friendly and scalable alternative to a wide spreadsheet. This structure separates high-level summaries from detailed, interactive data, allowing users to quickly assess the situation and then dive into specifics as needed. The interactive grid allows for easy status updates. -->
    <!-- Visualization & Content Choices: 
        - Report Info: '2025 머신러닝 입문 트랙 (7.15 - 7.25)' with 11 days of completion.
          - Goal: Show progress.
          - Viz/Presentation: Bar chart (Chart.js/Canvas) inside a summary card.
          - Interaction: The chart visually represents the completion percentage, which is more impactful than a row of 'O's.
          - Justification: Provides an immediate, high-level understanding of the team's achievement on the main task.
        - Report Info: Team members and the full date range for attendance.
          - Goal: Organize and track individual status.
          - Viz/Presentation: Interactive Grid (HTML/Tailwind/JS).
          - Interaction: Cells are clickable to toggle attendance status (e.g., 'present'), providing a simple data entry interface. Hovering shows the full date.
          - Justification: This transforms a static, hard-to-read table into a functional, interactive tool for daily tracking. It's far more usable, especially on smaller screens.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body { font-family: 'Noto Sans KR', sans-serif; }
        .chart-container { position: relative; width: 100%; max-width: 500px; margin-left: auto; margin-right: auto; height: 300px; }
        .grid-cell { transition: background-color 0.2s ease-in-out; }
        .present { background-color: #4ade80 !important; color: white; }
        .grid-header { position: sticky; top: 0; z-index: 10; }
    </style>
</head>
<body class="bg-slate-50 text-slate-800">

    <div class="container mx-auto p-4 sm:p-6 lg:p-8">
        
        <header class="text-center mb-10">
            <h1 class="text-3xl font-bold text-slate-900">팀 활동 대시보드</h1>
            <p class="text-md text-slate-600 mt-2">2025년 7월 15일 - 2025년 8월 22일</p>
        </header>

        <main class="space-y-12">
            
            <section id="events">
                <div class="max-w-3xl mx-auto">
                    <h2 class="text-2xl font-semibold mb-2 text-slate-800">주요 활동 진행 현황</h2>
                    <p class="text-slate-600 mb-6">
                        이 섹션에서는 팀의 핵심 활동 및 이벤트의 진행 상황을 요약하여 보여줍니다. 차트를 통해 현재 완료 상태를 직관적으로 파악할 수 있습니다.
                    </p>
                    <div class="bg-white p-6 rounded-xl shadow-md">
                        <h3 class="font-bold text-lg text-slate-900">2025 머신러닝 입문 트랙 (팀전)</h3>
                        <p class="text-sm text-slate-500 mb-4">기간: 2025.07.15 - 2025.07.25</p>
                        <div class="chart-container">
                            <canvas id="progressChart"></canvas>
                        </div>
                    </div>
                </div>
            </section>

            <section id="attendance">
                <div class="max-w-full mx-auto">
                    <h2 class="text-2xl font-semibold mb-2 text-slate-800">팀원별 출석 현황</h2>
                     <p class="text-slate-600 mb-6">
                        아래 표는 팀원들의 일자별 출석 상태를 나타냅니다. 각 날짜에 해당하는 칸을 클릭하여 출석(초록색) 여부를 표시하거나 해제할 수 있습니다. 표가 길 경우, 가로로 스크롤하여 모든 날짜를 확인할 수 있습니다.
                    </p>
                    <div class="bg-white rounded-xl shadow-md overflow-hidden">
                       <div class="overflow-x-auto">
                           <div id="attendanceGrid" class="p-4"></div>
                       </div>
                    </div>
                </div>
            </section>

        </main>
        
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            
            const teamData = {
                members: ['백승환', '이정주', '문규승', '오세울', '이재훈'],
                startDate: '2025-07-15',
                endDate: '2025-08-22',
            };

            const mlTrack = {
                name: '2025 머신러닝 입문 트랙',
                startDate: '2025-07-15',
                endDate: '2025-07-25',
                completedDays: 11,
            };

            function generateDates(start, end) {
                const dates = [];
                let currentDate = new Date(start);
                const endDate = new Date(end);
                while (currentDate <= endDate) {
                    dates.push(new Date(currentDate));
                    currentDate.setDate(currentDate.getDate() + 1);
                }
                return dates;
            }
            
            const allDates = generateDates(teamData.startDate, teamData.endDate);
            const mlTrackDates = generateDates(mlTrack.startDate, mlTrack.endDate);
            
            function renderAttendanceGrid() {
                const gridContainer = document.getElementById('attendanceGrid');
                
                let gridHtml = `<div class="grid" style="grid-template-columns: 150px repeat(${allDates.length}, 60px);">`;

                gridHtml += `<div class="font-bold text-slate-700 bg-slate-100 p-3 grid-header text-center flex items-center justify-center">팀원</div>`;
                allDates.forEach(date => {
                    gridHtml += `<div class="font-semibold text-sm text-slate-700 bg-slate-100 p-2 grid-header text-center flex items-center justify-center" title="${date.toLocaleDateString('ko-KR')}">${(date.getMonth() + 1)}/${date.getDate()}</div>`;
                });
                
                teamData.members.forEach(member => {
                    gridHtml += `<div class="font-semibold text-slate-800 bg-slate-50 p-3 flex items-center border-t border-slate-200">${member}</div>`;
                    allDates.forEach(date => {
                        const isMLTrackDate = date >= new Date(mlTrack.startDate) && date <= new Date(mlTrack.endDate);
                        const cellBg = isMLTrackDate ? 'bg-blue-50' : 'bg-white';
                        gridHtml += `<div class="grid-cell h-12 w-full border-t border-l border-slate-200 cursor-pointer hover:bg-slate-200 ${cellBg}" data-member="${member}" data-date="${date.toISOString().split('T')[0]}"></div>`;
                    });
                });

                gridHtml += '</div>';
                gridContainer.innerHTML = gridHtml;
                
                document.querySelectorAll('.grid-cell').forEach(cell => {
                    cell.addEventListener('click', () => {
                        cell.classList.toggle('present');
                    });
                });
            }

            function renderProgressChart() {
                const ctx = document.getElementById('progressChart').getContext('2d');
                
                const totalDays = mlTrackDates.length;
                const completedDays = mlTrack.completedDays;

                new Chart(ctx, {
                    type: 'bar',
                    data: {
                        labels: ['진행률'],
                        datasets: [{
                            label: '완료된 일수',
                            data: [completedDays],
                            backgroundColor: 'rgba(59, 130, 246, 0.7)',
                            borderColor: 'rgba(59, 130, 246, 1)',
                            borderWidth: 1
                        },
                        {
                            label: '남은 일수',
                            data: [totalDays - completedDays],
                            backgroundColor: 'rgba(226, 232, 240, 0.7)',
                            borderColor: 'rgba(203, 213, 225, 1)',
                            borderWidth: 1
                        }]
                    },
                    options: {
                        responsive: true,
                        maintainAspectRatio: false,
                        indexAxis: 'y',
                        scales: {
                            x: {
                                stacked: true,
                                max: totalDays,
                                grid: { display: false },
                                ticks: {
                                    callback: function(value) {
                                        return (value / totalDays * 100).toFixed(0) + '%';
                                    }
                                }
                            },
                            y: {
                                stacked: true,
                                grid: { display: false }
                            }
                        },
                        plugins: {
                            legend: {
                                position: 'top',
                            },
                            tooltip: {
                                callbacks: {
                                    label: function(context) {
                                        let label = context.dataset.label || '';
                                        if (label) {
                                            label += ': ';
                                        }
                                        if (context.parsed.x !== null) {
                                            label += `${context.parsed.x}일 (${(context.parsed.x / totalDays * 100).toFixed(1)}%)`;
                                        }
                                        return label;
                                    }
                                }
                            }
                        }
                    }
                });
            }

            renderAttendanceGrid();
            renderProgressChart();

        });
    </script>
</body>
</html>
