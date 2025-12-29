import React, { useState, useEffect } from 'react';
import { 
  CheckCircle2, 
  Circle, 
  Dumbbell, 
  Footprints, 
  Calendar, 
  Trophy, 
  ChevronRight, 
  ChevronLeft,
  Flame,
  Info,
  Clock,
  Plus,
  Save,
  X,
  TrendingUp,
  RotateCcw,
  ArrowUpCircle
} from 'lucide-react';

const DAYS = ['Lunes', 'Martes', 'Miércoles', 'Jueves', 'Viernes', 'Sábado', 'Domingo'];

// Estructura base que se adapta según la semana con progresión automática
const getWorkoutForWeek = (day, week) => {
  const data = {
    'Lunes': { type: 'fuerza', title: 'Upper Body & Handstand', focus: 'Empuje y Tracción', exercises: [
      { name: 'Pike Push-ups', target: `3 x ${8 + (week - 1)} reps` },
      { name: 'Wall Walks / Wall Hold', target: `${45 + (week - 1) * 5} seg` },
      { name: 'Fondos (Dips)', target: '3 x Fallo' },
      { name: 'Remos Invertidos', target: '3 x 10 reps' },
      { name: 'Rueda Abdominal', target: `3 x ${12 + (week - 1)} reps` }
    ]},
    'Martes': { type: 'running', title: 'Intervalos de Velocidad', focus: 'VO2 Max', tasks: [
      { name: 'Calentamiento', target: '10 min Trote' },
      { name: 'Series 800m', target: `${6 + (week > 2 ? 2 : 0)} reps` },
      { name: 'Descanso', target: '2 min caminando' }
    ]},
    'Miércoles': { type: 'fuerza', title: 'Lower Body & Stability', focus: 'Piernas Ironman', exercises: [
      { name: 'Zancada Búlgara', target: '3 x 12 p/p' },
      { name: 'Puentes de Glúteo', target: '3 x 20 reps' },
      { name: 'Elevación Talones', target: '3 x 30 reps' },
      { name: 'Máquina de Abs', target: '3 x 15 reps' }
    ]},
    'Jueves': { type: 'running', title: 'Tempo Run', focus: 'Resistencia Aeróbica', tasks: [
      { name: 'Distancia Objetivo', target: `${8 + (week - 1)} km` },
      { name: 'Cadencia alta', target: '180 spm' }
    ]},
    'Viernes': { type: 'fuerza', title: 'Full Body & Core', focus: 'Técnica Handstand', exercises: [
      { name: 'Práctica Handstand', target: `${15 + (week - 1) * 2} min` },
      { name: 'Flexiones Diamante', target: '3 x Fallo' },
      { name: 'Rueda Abdominal', target: '4 x 10 reps' }
    ]},
    'Sábado': { type: 'running', title: 'Long Run (Base Ironman)', focus: 'Resistencia Ultra', tasks: [
      { name: 'Distancia Larga', target: `${15 + (week - 1) * 2} km` },
      { name: 'Prueba de Nutrición', target: 'Hidratación/Geles' }
    ]},
    'Domingo': { type: 'rest', title: 'Descanso / Movilidad', focus: 'Recuperación', tasks: [
      { name: 'Estiramiento Global', target: '15 min' },
      { name: 'Movilidad Hombros', target: '10 min' }
    ]}
  };
  return data[day];
};

const App = () => {
  const [activeTab, setActiveTab] = useState('today'); 
  const [currentDayIndex, setCurrentDayIndex] = useState(0);
  const [week, setWeek] = useState(1);
  const [completedExercises, setCompletedExercises] = useState({});
  const [runStats, setRunStats] = useState({});
  const [showAddModal, setShowAddModal] = useState(false);
  const [note, setNote] = useState("");

  useEffect(() => {
    // Configura el día actual al abrir
    const today = new Date().getDay();
    setCurrentDayIndex(today === 0 ? 6 : today - 1);
    
    try {
      const savedWeek = localStorage.getItem('califest_week');
      const savedProgress = localStorage.getItem('califest_progress');
      const savedRuns = localStorage.getItem('califest_runs');
      
      if (savedWeek) setWeek(parseInt(savedWeek));
      if (savedProgress) setCompletedExercises(JSON.parse(savedProgress));
      if (savedRuns) setRunStats(JSON.parse(savedRuns));
    } catch (e) {
      console.error("Error cargando datos del storage", e);
    }
  }, []);

  const toggleExercise = (name) => {
    const key = `W${week}-${DAYS[currentDayIndex]}-${name}`;
    const updated = { ...completedExercises, [key]: !completedExercises[key] };
    setCompletedExercises(updated);
    localStorage.setItem('califest_progress', JSON.stringify(updated));
  };

  const advanceWeek = () => {
    const nextWeek = week + 1;
    setWeek(nextWeek);
    localStorage.setItem('califest_week', nextWeek.toString());
    setActiveTab('today');
    window.scrollTo(0, 0);
  };

  const resetAll = () => {
    // Reemplazo de confirm por un modal custom o simple logic para entorno web
    if(window.confirm("¿Seguro que quieres reiniciar todo el progreso desde la Semana 1?")) {
      setWeek(1);
      setCompletedExercises({});
      setRunStats({});
      localStorage.clear();
      window.location.reload();
    }
  };

  const handleRunInput = (field, val) => {
    const dayKey = `W${week}-${DAYS[currentDayIndex]}`;
    const updated = { ...runStats, [dayKey]: { ...runStats[dayKey], [field]: val } };
    setRunStats(updated);
    localStorage.setItem('califest_runs', JSON.stringify(updated));
  };

  const currentDayName = DAYS[currentDayIndex];
  const workout = getWorkoutForWeek(currentDayName, week);

  const calculateDayProgress = (dayName) => {
    const dayWorkout = getWorkoutForWeek(dayName, week);
    const dayItems = (dayWorkout.exercises || dayWorkout.tasks);
    const done = dayItems.filter(i => completedExercises[`W${week}-${dayName}-${i.name}`]).length;
    return { done, total: dayItems.length };
  };

  const calculateTotalProgress = () => {
    let totalItems = 0;
    let completed = 0;
    DAYS.forEach(day => {
      const p = calculateDayProgress(day);
      totalItems += p.total;
      completed += p.done;
    });
    if (totalItems === 0) return 0;
    return Math.round((completed / totalItems) * 100);
  };

  return (
    <div className="min-h-screen bg-black text-white font-sans pb-32 selection:bg-[#deff9a] selection:text-black">
      
      {/* Header Interactivo */}
      <header className="p-6 bg-neutral-900/90 border-b border-[#deff9a]/20 sticky top-0 z-30 backdrop-blur-xl">
        <div className="flex justify-between items-center mb-6">
          <div>
            <h1 className="text-2xl font-black text-[#deff9a] italic tracking-tighter">CALI FEST 2025</h1>
            <p className="text-[10px] text-neutral-500 font-bold uppercase tracking-[0.3em]">Semana {week.toString().padStart(2, '0')}</p>
          </div>
          <div className="flex flex-col items-end">
            <span className="text-2xl font-black text-white">{calculateTotalProgress()}%</span>
            <div className="w-20 h-1 bg-neutral-800 rounded-full mt-1 overflow-hidden">
               <div className="h-full bg-[#deff9a] transition-all duration-1000" style={{ width: `${calculateTotalProgress()}%` }}></div>
            </div>
          </div>
        </div>

        {activeTab === 'today' && (
          <div className="flex items-center justify-between bg-black/40 p-2 rounded-2xl border border-white/5">
            <button onClick={() => setCurrentDayIndex(p => (p - 1 + 7) % 7)} className="p-2 hover:bg-white/5 rounded-full transition active:scale-90">
              <ChevronLeft size={20} />
            </button>
            <div className="text-center">
              <h2 className="text-sm font-black uppercase tracking-widest text-[#deff9a]">{currentDayName}</h2>
            </div>
            <button onClick={() => setCurrentDayIndex(p => (p + 1) % 7)} className="p-2 hover:bg-white/5 rounded-full transition active:scale-90">
              <ChevronRight size={20} />
            </button>
          </div>
        )}
      </header>

      <main className="p-5 max-w-md mx-auto">
        {activeTab === 'today' ? (
          <div className="animate-in fade-in zoom-in-95 duration-300">
            <div className={`rounded-[2.5rem] p-8 mb-6 border transition-all duration-700 ${
              workout.type === 'fuerza' ? 'bg-indigo-600/10 border-indigo-500/30 shadow-[0_0_40px_rgba(79,70,229,0.1)]' : 
              workout.type === 'running' ? 'bg-emerald-600/10 border-emerald-500/30 shadow-[0_0_40px_rgba(16,185,129,0.1)]' : 
              'bg-neutral-900 border-neutral-700'
            }`}>
              <div className="flex items-center gap-4 mb-8">
                <div className={`p-4 rounded-2xl shadow-lg ${
                   workout.type === 'fuerza' ? 'bg-indigo-500/20 text-indigo-400' : 
                   workout.type === 'running' ? 'bg-emerald-500/20 text-emerald-400' : 'bg-neutral-800 text-neutral-400'
                }`}>
                  {workout.type === 'fuerza' ? <Dumbbell /> : workout.type === 'running' ? <Footprints /> : <Clock />}
                </div>
                <div>
                  <h3 className="text-xl font-black leading-tight uppercase italic">{workout.title}</h3>
                  <p className="text-[10px] text-neutral-500 font-bold uppercase tracking-widest">{workout.focus}</p>
                </div>
              </div>

              <div className="space-y-3">
                {(workout.exercises || workout.tasks).map((item, idx) => {
                  const isDone = completedExercises[`W${week}-${currentDayName}-${item.name}`];
                  return (
                    <button
                      key={idx}
                      onClick={() => toggleExercise(item.name)}
                      className={`w-full flex items-center gap-4 p-5 rounded-3xl border transition-all duration-300 ${
                        isDone ? 'bg-neutral-900/50 border-transparent opacity-40 scale-95' : 'bg-neutral-800/40 border-white/5 shadow-xl active:scale-95'
                      }`}
                    >
                      {isDone ? <CheckCircle2 className="text-[#deff9a]" size={24} /> : <Circle className="text-neutral-700" size={24} />}
                      <div className="text-left flex-1">
                        <p className={`text-sm font-black ${isDone ? 'line-through text-neutral-600' : 'text-white'}`}>{item.name}</p>
                        <p className="text-[10px] text-neutral-500 font-bold uppercase mt-1 tracking-tighter">{item.target}</p>
                      </div>
                    </button>
                  );
                })}
              </div>

              {workout.type === 'running' && (
                <div className="mt-10 pt-8 border-t border-white/5">
                  <div className="flex items-center justify-between mb-4">
                    <h4 className="text-[10px] font-black text-[#deff9a] uppercase tracking-[0.2em]">Log de Carrera</h4>
                    <Trophy size={14} className="text-[#deff9a] opacity-50" />
                  </div>
                  <div className="grid grid-cols-2 gap-4">
                    <div className="bg-black/40 rounded-2xl p-4 border border-white/5">
                      <span className="text-[8px] text-neutral-600 font-bold uppercase block mb-1">Kilómetros</span>
                      <input 
                        type="number" 
                        inputMode="decimal"
                        placeholder="0.0" 
                        value={runStats[`W${week}-${currentDayName}`]?.km || ''}
                        onChange={(e) => handleRunInput('km', e.target.value)}
                        className="bg-transparent w-full text-lg font-black outline-none text-[#deff9a]"
                      />
                    </div>
                    <div className="bg-black/40 rounded-2xl p-4 border border-white/5">
                      <span className="text-[8px] text-neutral-600 font-bold uppercase block mb-1">Minutos</span>
                      <input 
                        type="number" 
                        inputMode="numeric"
                        placeholder="0" 
                        value={runStats[`W${week}-${currentDayName}`]?.min || ''}
                        onChange={(e) => handleRunInput('min', e.target.value)}
                        className="bg-transparent w-full text-lg font-black outline-none text-white"
                      />
                    </div>
                  </div>
                </div>
              )}
            </div>
          </div>
        ) : (
          <div className="space-y-6 animate-in fade-in slide-in-from-bottom-4 duration-300">
            <div className="flex justify-between items-end mb-4 px-2">
              <h3 className="text-2xl font-black italic tracking-tighter text-white uppercase">Progreso Semanal</h3>
              <button onClick={resetAll} className="text-[9px] text-red-500 font-bold flex items-center gap-1 uppercase bg-red-500/10 px-2 py-1 rounded-md">
                <RotateCcw size={10} /> Reset Total
              </button>
            </div>
            
            <div className="space-y-3">
              {DAYS.map(day => {
                const { done, total } = calculateDayProgress(day);
                const isComplete = done === total;
                return (
                  <div key={day} className={`p-5 rounded-[2rem] border transition-all ${isComplete ? 'bg-[#deff9a]/5 border-[#deff9a]/20' : 'bg-neutral-900 border-white/5'}`}>
                    <div className="flex justify-between items-center">
                      <div>
                        <p className={`text-xs font-black uppercase ${isComplete ? 'text-[#deff9a]' : 'text-neutral-400'}`}>{day}</p>
                        <p className="text-[10px] text-neutral-600 font-bold">{getWorkoutForWeek(day, week).title}</p>
                      </div>
                      <div className="flex items-center gap-4">
                        <div className="text-right">
                          <p className="text-xs font-black italic">{done}/{total}</p>
                        </div>
                        {isComplete ? <CheckCircle2 size={20} className="text-[#deff9a]" /> : <div className="w-5 h-5 rounded-full border-2 border-neutral-800" />}
                      </div>
                    </div>
                  </div>
                );
              })}
            </div>

            <div className="pt-6">
              <button 
                onClick={advanceWeek}
                disabled={calculateTotalProgress() < 80}
                className={`w-full py-6 rounded-3xl font-black italic text-lg flex items-center justify-center gap-3 transition-all ${
                  calculateTotalProgress() >= 80 
                  ? 'bg-[#deff9a] text-black shadow-[0_15px_30px_rgba(222,255,154,0.3)] scale-100 active:scale-95' 
                  : 'bg-neutral-800 text-neutral-500 opacity-50 cursor-not-allowed'
                }`}
              >
                <ArrowUpCircle size={24} />
                EMPEZAR SEMANA {week + 1}
              </button>
              {calculateTotalProgress() < 80 && (
                <p className="text-[10px] text-center text-neutral-500 mt-4 uppercase font-bold tracking-widest">
                  Completa al menos el 80% para avanzar
                </p>
              )}
            </div>
          </div>
        )}
      </main>

      {/* Modal Logs Personales */}
      {showAddModal && (
        <div className="fixed inset-0 z-50 flex items-center justify-center p-6 bg-black/95 backdrop-blur-md animate-in zoom-in-95 duration-200">
          <div className="bg-neutral-900 w-full max-w-sm rounded-[3rem] p-10 border border-white/10 shadow-2xl">
            <div className="flex justify-between items-center mb-8">
              <h3 className="text-2xl font-black italic text-[#deff9a]">NOTAS ELITE</h3>
              <button onClick={() => setShowAddModal(false)} className="bg-white/5 p-2 rounded-full"><X size={20}/></button>
            </div>
            <textarea 
              className="w-full bg-black rounded-[2rem] p-6 text-sm border border-white/5 h-40 outline-none focus:border-[#deff9a]/50 font-medium transition-all"
              placeholder="¿Qué rompiste hoy? ¿Más segundos de handstand? ¿Algún nuevo récord?"
              value={note}
              onChange={(e) => setNote(e.target.value)}
            />
            <button 
              onClick={() => { 
                if (note.trim()) {
                  const logs = JSON.parse(localStorage.getItem('califest_logs') || '[]');
                  logs.push({ date: new Date().toISOString(), week, note });
                  localStorage.setItem('califest_logs', JSON.stringify(logs));
                }
                setShowAddModal(false); 
                setNote(""); 
              }}
              className="w-full bg-[#deff9a] text-black font-black py-5 rounded-[2rem] mt-6 flex items-center justify-center gap-3 shadow-lg active:scale-95 transition-transform"
            >
              <Save size={20} /> GUARDAR RÉCORD
            </button>
          </div>
        </div>
      )}

      {/* Nav Bar Mobile Optimized */}
      <nav className="fixed bottom-0 left-0 right-0 bg-neutral-950/90 backdrop-blur-3xl border-t border-white/5 px-10 py-7 flex justify-around items-center z-40">
        <button 
          onClick={() => setActiveTab('today')}
          className={`flex flex-col items-center gap-1.5 transition-all duration-300 ${activeTab === 'today' ? 'text-[#deff9a] scale-110 drop-shadow-[0_0_10px_rgba(222,255,154,0.4)]' : 'text-neutral-600'}`}
        >
          <Calendar size={24} strokeWidth={activeTab === 'today' ? 3 : 2} />
          <span className="text-[9px] font-black uppercase tracking-tighter">Diario</span>
        </button>
        
        <button 
          onClick={() => setShowAddModal(true)}
          className="w-16 h-16 bg-[#deff9a] rounded-full flex items-center justify-center -mt-14 shadow-[0_15px_35px_rgba(222,255,154,0.4)] active:scale-90 transition-all border-4 border-black"
        >
          <Plus size={32} className="text-black" strokeWidth={3} />
        </button>

        <button 
          onClick={() => setActiveTab('progress')}
          className={`flex flex-col items-center gap-1.5 transition-all duration-300 ${activeTab === 'progress' ? 'text-[#deff9a] scale-110 drop-shadow-[0_0_10px_rgba(222,255,154,0.4)]' : 'text-neutral-600'}`}
        >
          <TrendingUp size={24} strokeWidth={activeTab === 'progress' ? 3 : 2} />
          <span className="text-[9px] font-black uppercase tracking-tighter">Estado</span>
        </button>
      </nav>
    </div>
  );
};

export default App;
