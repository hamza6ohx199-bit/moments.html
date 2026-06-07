<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>مذكرة اللحظات السعيدة ✨</title>
<meta name="description" content="سجّل لحظاتك السعيدة مع الصور واحتفظ بذكرياتك الجميلة إلى الأبد"/>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;900&display=swap" rel="stylesheet"/>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<style>
/* ============ THEME VARIABLES ============ */
:root {
  --gold:#f5c842;--gold-light:#ffe680;
  --rose:#ff6b9d;--rose-light:#ffb3cd;
  --purple:#a855f7;--purple-dark:#7c3aed;
  --sky:#38bdf8;--green:#34d399;
  --bg-dark:#0f0a1e;--bg-card:rgba(255,255,255,0.05);
  --bg-card-hover:rgba(255,255,255,0.09);
  --border:rgba(255,255,255,0.1);
  --text-main:#f0e6ff;--text-sub:#b4a8cc;
  --shadow-glow:0 0 40px rgba(168,85,247,0.3);
  --bg-body:#0f0a1e;--bg-page:#0f0a1e;
}
body.light {
  --bg-dark:#f5f0ff;--bg-body:#f5f0ff;--bg-page:#f5f0ff;
  --bg-card:rgba(255,255,255,0.8);--bg-card-hover:rgba(255,255,255,0.95);
  --border:rgba(0,0,0,0.1);--text-main:#1a0a3e;--text-sub:#6b5b8a;
  --shadow-glow:0 0 40px rgba(168,85,247,0.15);
}
*{margin:0;padding:0;box-sizing:border-box;}
body{font-family:'Tajawal',sans-serif;background:var(--bg-body);color:var(--text-main);min-height:100vh;overflow-x:hidden;position:relative;transition:background 0.4s,color 0.4s;}
body::before{content:'';position:fixed;inset:0;background:radial-gradient(ellipse 80% 50% at 20% 20%,rgba(168,85,247,0.15) 0%,transparent 60%),radial-gradient(ellipse 60% 40% at 80% 80%,rgba(255,107,157,0.12) 0%,transparent 60%);pointer-events:none;z-index:0;transition:opacity 0.4s;}
body.light::before{opacity:0.4;}

/* ============ PARTICLES ============ */
.particles{position:fixed;inset:0;pointer-events:none;z-index:0;overflow:hidden;}
.particle{position:absolute;border-radius:50%;opacity:0.4;animation:float-particle linear infinite;}
@keyframes float-particle{0%{transform:translateY(100vh) rotate(0deg);opacity:0;}10%{opacity:0.4;}90%{opacity:0.4;}100%{transform:translateY(-20px) rotate(720deg);opacity:0;}}

/* ============ TOP BAR ============ */
.top-bar{position:sticky;top:0;z-index:100;display:flex;align-items:center;justify-content:space-between;padding:0.75rem 1.5rem;background:rgba(15,10,30,0.85);backdrop-filter:blur(20px);border-bottom:1px solid var(--border);transition:background 0.4s;}
body.light .top-bar{background:rgba(245,240,255,0.9);}
.top-bar-logo{font-size:1.3rem;font-weight:900;background:linear-gradient(135deg,var(--gold),var(--rose),var(--purple));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
.top-bar-actions{display:flex;gap:0.6rem;align-items:center;}
.icon-btn{background:var(--bg-card);border:1px solid var(--border);border-radius:10px;padding:0.45rem 0.8rem;color:var(--text-main);font-size:1rem;cursor:pointer;transition:all 0.25s;display:flex;align-items:center;gap:0.35rem;font-family:'Tajawal',sans-serif;white-space:nowrap;}
.icon-btn:hover{background:var(--bg-card-hover);border-color:var(--purple);}
.icon-btn.active-view{background:linear-gradient(135deg,rgba(168,85,247,0.3),rgba(255,107,157,0.3));border-color:var(--purple);}

/* ============ HEADER ============ */
header{position:relative;z-index:10;text-align:center;padding:2.5rem 1rem 1.5rem;}
.header-icon{font-size:3.5rem;display:block;margin-bottom:0.4rem;animation:pulse-icon 3s ease-in-out infinite;filter:drop-shadow(0 0 20px rgba(245,200,66,0.6));}
@keyframes pulse-icon{0%,100%{transform:scale(1);}50%{transform:scale(1.1);}}
h1{font-size:2.5rem;font-weight:900;background:linear-gradient(135deg,var(--gold),var(--rose),var(--purple));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;line-height:1.3;}
.subtitle{color:var(--text-sub);font-size:1rem;margin-top:0.3rem;}

/* ============ CONTAINER ============ */
.container{position:relative;z-index:5;max-width:1150px;margin:0 auto;padding:0 1.5rem 4rem;}

/* ============ STATS ============ */
.stats-bar{display:flex;gap:0.8rem;justify-content:center;flex-wrap:wrap;margin-bottom:2rem;}
.stat-chip{background:var(--bg-card);border:1px solid var(--border);border-radius:50px;padding:0.45rem 1.1rem;font-size:0.88rem;display:flex;align-items:center;gap:0.4rem;backdrop-filter:blur(10px);transition:all 0.3s;}
.stat-chip:hover{border-color:rgba(168,85,247,0.4);background:var(--bg-card-hover);}
.stat-chip strong{color:var(--gold);}

/* ============ TABS ============ */
.tabs{display:flex;gap:0.5rem;margin-bottom:1.5rem;background:var(--bg-card);border:1px solid var(--border);border-radius:16px;padding:0.4rem;backdrop-filter:blur(10px);}
.tab-btn{flex:1;background:transparent;border:none;border-radius:12px;padding:0.6rem;color:var(--text-sub);font-family:'Tajawal',sans-serif;font-size:0.95rem;cursor:pointer;transition:all 0.25s;display:flex;align-items:center;justify-content:center;gap:0.4rem;}
.tab-btn.active{background:linear-gradient(135deg,var(--purple-dark),var(--rose));color:white;box-shadow:0 4px 15px rgba(168,85,247,0.4);}
.tab-content{display:none;}
.tab-content.active{display:block;}

/* ============ FORM ============ */
.form-card{background:var(--bg-card);border:1px solid var(--border);border-radius:24px;padding:2rem;margin-bottom:2rem;backdrop-filter:blur(20px);box-shadow:var(--shadow-glow);transition:all 0.3s;}
.form-card:hover{border-color:rgba(168,85,247,0.3);}
.form-title{font-size:1.2rem;font-weight:700;margin-bottom:1.3rem;display:flex;align-items:center;gap:0.5rem;}
.form-grid{display:grid;grid-template-columns:1fr 1fr;gap:1rem;}
.form-group{display:flex;flex-direction:column;gap:0.45rem;}
.form-group.full-width{grid-column:1/-1;}
label{font-size:0.88rem;color:var(--text-sub);font-weight:500;}
input[type="text"],input[type="date"],textarea,select{background:rgba(255,255,255,0.07);border:1px solid var(--border);border-radius:12px;padding:0.7rem 1rem;color:var(--text-main);font-family:'Tajawal',sans-serif;font-size:0.97rem;outline:none;transition:all 0.3s;width:100%;direction:rtl;}
body.light input[type="text"],body.light input[type="date"],body.light textarea,body.light select{background:rgba(255,255,255,0.9);color:#1a0a3e;}
input:focus,textarea:focus,select:focus{border-color:var(--purple);background:rgba(168,85,247,0.08);box-shadow:0 0 0 3px rgba(168,85,247,0.15);}
textarea{resize:vertical;min-height:100px;line-height:1.7;}
select option{background:#1a1030;color:var(--text-main);}

/* Mood */
.mood-selector{display:flex;gap:0.45rem;flex-wrap:wrap;}
.mood-btn{background:rgba(255,255,255,0.05);border:2px solid transparent;border-radius:10px;padding:0.45rem 0.7rem;font-size:1.3rem;cursor:pointer;transition:all 0.25s;display:flex;align-items:center;gap:0.25rem;}
.mood-btn span.mood-label{font-size:0.72rem;color:var(--text-sub);font-family:'Tajawal',sans-serif;}
.mood-btn:hover{transform:scale(1.1);background:rgba(168,85,247,0.15);}
.mood-btn.active{border-color:var(--purple);background:rgba(168,85,247,0.2);box-shadow:0 0 15px rgba(168,85,247,0.3);}

/* Upload */
.photo-upload-area{border:2px dashed var(--border);border-radius:14px;padding:1.3rem;text-align:center;cursor:pointer;transition:all 0.3s;position:relative;overflow:hidden;}
.photo-upload-area:hover{border-color:var(--purple);background:rgba(168,85,247,0.05);}
.photo-upload-area.drag-over{border-color:var(--gold);background:rgba(245,200,66,0.05);}
.photo-upload-area input[type="file"]{position:absolute;inset:0;opacity:0;cursor:pointer;width:100%;height:100%;}
.upload-icon{font-size:2rem;margin-bottom:0.4rem;}
.upload-text{color:var(--text-sub);font-size:0.88rem;}
.upload-text strong{color:var(--purple);}
.preview-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(75px,1fr));gap:0.5rem;margin-top:0.8rem;}
.preview-item{position:relative;aspect-ratio:1;border-radius:10px;overflow:hidden;border:2px solid var(--border);}
.preview-item img{width:100%;height:100%;object-fit:cover;}
.preview-item .remove-img{position:absolute;top:3px;right:3px;background:rgba(0,0,0,0.7);border:none;border-radius:50%;width:20px;height:20px;color:white;font-size:0.7rem;cursor:pointer;display:flex;align-items:center;justify-content:center;transition:all 0.2s;}
.preview-item .remove-img:hover{background:#e11d48;}

/* Submit */
.btn-submit{width:100%;padding:0.95rem;border:none;border-radius:14px;background:linear-gradient(135deg,var(--purple-dark),var(--rose));color:white;font-family:'Tajawal',sans-serif;font-size:1.1rem;font-weight:700;cursor:pointer;margin-top:1.3rem;transition:all 0.3s;box-shadow:0 8px 30px rgba(168,85,247,0.4);position:relative;overflow:hidden;}
.btn-submit::before{content:'';position:absolute;top:50%;left:50%;width:0;height:0;background:rgba(255,255,255,0.2);border-radius:50%;transform:translate(-50%,-50%);transition:width 0.5s,height 0.5s;}
.btn-submit:hover::before{width:400px;height:400px;}
.btn-submit:hover{transform:translateY(-2px);box-shadow:0 12px 40px rgba(168,85,247,0.6);}

/* ============ FILTERS ============ */
.filters-bar{display:flex;gap:0.6rem;margin-bottom:1.2rem;flex-wrap:wrap;align-items:center;}
.filter-btn{background:var(--bg-card);border:1px solid var(--border);border-radius:50px;padding:0.4rem 0.95rem;color:var(--text-sub);font-family:'Tajawal',sans-serif;font-size:0.88rem;cursor:pointer;transition:all 0.25s;backdrop-filter:blur(10px);}
.filter-btn:hover,.filter-btn.active{background:linear-gradient(135deg,rgba(168,85,247,0.3),rgba(255,107,157,0.3));border-color:var(--purple);color:var(--text-main);}
.search-box{flex:1;min-width:180px;background:var(--bg-card);border:1px solid var(--border);border-radius:50px;padding:0.48rem 1rem;color:var(--text-main);font-family:'Tajawal',sans-serif;font-size:0.93rem;outline:none;transition:all 0.3s;direction:rtl;}
.search-box:focus{border-color:var(--purple);box-shadow:0 0 0 3px rgba(168,85,247,0.15);}

/* ============ MOMENTS GRID ============ */
.moments-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:1.3rem;}
.moment-card{background:var(--bg-card);border:1px solid var(--border);border-radius:20px;overflow:hidden;backdrop-filter:blur(15px);transition:all 0.35s cubic-bezier(0.175,0.885,0.32,1.275);animation:card-in 0.4s ease both;position:relative;}
@keyframes card-in{from{opacity:0;transform:translateY(20px) scale(0.95);}to{opacity:1;transform:translateY(0) scale(1);}}
.moment-card:hover{transform:translateY(-6px);border-color:rgba(168,85,247,0.4);box-shadow:0 20px 50px rgba(168,85,247,0.2);}
.card-gallery{position:relative;overflow:hidden;max-height:200px;}
.card-gallery img{width:100%;height:200px;object-fit:cover;display:block;transition:transform 0.5s;cursor:zoom-in;}
.moment-card:hover .card-gallery img{transform:scale(1.05);}
.gallery-count{position:absolute;bottom:8px;left:8px;background:rgba(0,0,0,0.7);backdrop-filter:blur(5px);border-radius:20px;padding:3px 10px;font-size:0.78rem;color:white;}
.card-content{padding:1.1rem;}
.card-header{display:flex;align-items:flex-start;justify-content:space-between;gap:0.5rem;margin-bottom:0.6rem;}
.card-title{font-size:1.05rem;font-weight:700;line-height:1.4;flex:1;}
.card-mood{font-size:1.6rem;}
.card-meta{display:flex;gap:0.6rem;flex-wrap:wrap;margin-bottom:0.6rem;}
.meta-tag{display:flex;align-items:center;gap:0.25rem;font-size:0.78rem;color:var(--text-sub);background:rgba(255,255,255,0.06);padding:2px 8px;border-radius:20px;}
.card-desc{font-size:0.92rem;color:var(--text-sub);line-height:1.65;margin-bottom:0.8rem;display:-webkit-box;-webkit-line-clamp:3;-webkit-box-orient:vertical;overflow:hidden;}
.card-category{display:inline-block;padding:2px 10px;border-radius:20px;font-size:0.78rem;font-weight:500;margin-bottom:0.7rem;}
.category-family{background:rgba(56,189,248,0.2);color:var(--sky);}
.category-friends{background:rgba(255,107,157,0.2);color:var(--rose);}
.category-achievement{background:rgba(245,200,66,0.2);color:var(--gold);}
.category-nature{background:rgba(52,211,153,0.2);color:var(--green);}
.category-travel{background:rgba(168,85,247,0.2);color:var(--purple);}
.category-other{background:rgba(255,255,255,0.1);color:var(--text-sub);}
.card-actions{display:flex;gap:0.4rem;border-top:1px solid var(--border);padding-top:0.7rem;flex-wrap:wrap;}
.action-btn{flex:1;min-width:70px;background:transparent;border:1px solid var(--border);border-radius:9px;padding:0.42rem 0.5rem;color:var(--text-sub);font-family:'Tajawal',sans-serif;font-size:0.82rem;cursor:pointer;transition:all 0.25s;display:flex;align-items:center;justify-content:center;gap:0.25rem;}
.action-btn:hover{background:rgba(255,255,255,0.08);color:var(--text-main);}
.action-btn.delete:hover{background:rgba(239,68,68,0.15);border-color:rgba(239,68,68,0.4);color:#f87171;}
.action-btn.favorite{color:var(--gold);}
.action-btn.favorite:hover{background:rgba(245,200,66,0.15);border-color:rgba(245,200,66,0.4);}
.no-image-banner{background:linear-gradient(135deg,rgba(168,85,247,0.2),rgba(255,107,157,0.2));height:110px;display:flex;align-items:center;justify-content:center;font-size:2.8rem;}
.moment-card.is-favorite::after{content:'⭐';position:absolute;top:10px;right:10px;font-size:1.1rem;filter:drop-shadow(0 0 8px rgba(245,200,66,0.8));}
.empty-state{text-align:center;padding:3.5rem 2rem;grid-column:1/-1;}
.empty-icon{font-size:4.5rem;margin-bottom:0.8rem;opacity:0.5;}
.empty-title{font-size:1.3rem;font-weight:700;margin-bottom:0.4rem;}
.empty-subtitle{color:var(--text-sub);}

/* ============ CALENDAR ============ */
.calendar-wrap{background:var(--bg-card);border:1px solid var(--border);border-radius:24px;padding:1.5rem;backdrop-filter:blur(20px);}
.cal-header{display:flex;align-items:center;justify-content:space-between;margin-bottom:1.2rem;}
.cal-title{font-size:1.2rem;font-weight:700;}
.cal-nav{background:var(--bg-card);border:1px solid var(--border);border-radius:10px;width:36px;height:36px;display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:1rem;transition:all 0.2s;color:var(--text-main);}
.cal-nav:hover{background:var(--bg-card-hover);border-color:var(--purple);}
.cal-weekdays{display:grid;grid-template-columns:repeat(7,1fr);gap:4px;margin-bottom:4px;}
.cal-weekday{text-align:center;font-size:0.8rem;color:var(--text-sub);padding:6px 0;font-weight:600;}
.cal-days{display:grid;grid-template-columns:repeat(7,1fr);gap:4px;}
.cal-day{aspect-ratio:1;border-radius:10px;display:flex;flex-direction:column;align-items:center;justify-content:center;font-size:0.9rem;cursor:pointer;transition:all 0.2s;border:1px solid transparent;position:relative;}
.cal-day:hover{background:rgba(168,85,247,0.15);border-color:var(--purple);}
.cal-day.empty{opacity:0;}
.cal-day.today{background:rgba(168,85,247,0.2);border-color:var(--purple);font-weight:700;color:var(--purple);}
.cal-day.has-moment{border-color:var(--gold);}
.cal-day.has-moment::after{content:'';position:absolute;bottom:4px;width:5px;height:5px;border-radius:50%;background:var(--gold);}
.cal-day.selected{background:linear-gradient(135deg,var(--purple-dark),var(--rose));color:white;border:none;}
.cal-events{margin-top:1.3rem;display:flex;flex-direction:column;gap:0.6rem;}
.cal-event-item{background:var(--bg-card-hover);border:1px solid var(--border);border-radius:12px;padding:0.75rem 1rem;display:flex;align-items:center;gap:0.8rem;transition:all 0.2s;cursor:pointer;}
.cal-event-item:hover{border-color:var(--purple);}
.cal-event-emoji{font-size:1.5rem;}
.cal-event-info{flex:1;}
.cal-event-title{font-size:0.95rem;font-weight:600;}
.cal-event-date{font-size:0.8rem;color:var(--text-sub);}

/* ============ REMINDERS ============ */
.reminder-section{background:var(--bg-card);border:1px solid var(--border);border-radius:24px;padding:1.5rem;backdrop-filter:blur(20px);}
.reminder-header{display:flex;align-items:center;justify-content:space-between;margin-bottom:1.3rem;}
.reminder-title{font-size:1.15rem;font-weight:700;display:flex;align-items:center;gap:0.5rem;}
.toggle-switch{position:relative;width:52px;height:27px;}
.toggle-switch input{opacity:0;width:0;height:0;}
.toggle-slider{position:absolute;cursor:pointer;inset:0;background:rgba(255,255,255,0.1);border-radius:50px;transition:all 0.3s;border:1px solid var(--border);}
.toggle-slider::before{content:'';position:absolute;height:19px;width:19px;left:4px;bottom:3px;background:var(--text-sub);border-radius:50%;transition:all 0.3s;}
.toggle-switch input:checked + .toggle-slider{background:var(--purple);border-color:var(--purple);}
.toggle-switch input:checked + .toggle-slider::before{transform:translateX(25px);background:white;}
.reminder-form{display:flex;flex-direction:column;gap:0.8rem;}
.reminder-row{display:flex;gap:0.8rem;align-items:center;flex-wrap:wrap;}
.reminder-row label{font-size:0.9rem;color:var(--text-sub);white-space:nowrap;}
.reminder-input{background:rgba(255,255,255,0.07);border:1px solid var(--border);border-radius:10px;padding:0.55rem 0.9rem;color:var(--text-main);font-family:'Tajawal',sans-serif;font-size:0.95rem;outline:none;transition:all 0.3s;}
body.light .reminder-input{background:rgba(255,255,255,0.9);color:#1a0a3e;}
.reminder-input:focus{border-color:var(--purple);box-shadow:0 0 0 3px rgba(168,85,247,0.15);}
.reminder-msg{padding:0.8rem 1rem;border-radius:12px;font-size:0.9rem;text-align:center;}
.reminder-msg.success{background:rgba(52,211,153,0.15);border:1px solid rgba(52,211,153,0.3);color:var(--green);}
.reminder-msg.warning{background:rgba(245,200,66,0.15);border:1px solid rgba(245,200,66,0.3);color:var(--gold);}
.reminder-msg.error{background:rgba(239,68,68,0.15);border:1px solid rgba(239,68,68,0.3);color:#f87171;}
.notif-perms{display:flex;flex-direction:column;gap:0.6rem;}

/* ============ PDF EXPORT ============ */
.export-section{background:var(--bg-card);border:1px solid var(--border);border-radius:24px;padding:1.5rem;backdrop-filter:blur(20px);margin-bottom:1.3rem;}
.export-title{font-size:1.15rem;font-weight:700;margin-bottom:1rem;display:flex;align-items:center;gap:0.5rem;}
.export-options{display:grid;grid-template-columns:repeat(auto-fill,minmax(160px,1fr));gap:0.8rem;}
.export-btn{background:var(--bg-card-hover);border:1px solid var(--border);border-radius:14px;padding:1rem;display:flex;flex-direction:column;align-items:center;gap:0.5rem;cursor:pointer;transition:all 0.3s;font-family:'Tajawal',sans-serif;color:var(--text-main);font-size:0.9rem;text-align:center;}
.export-btn:hover{transform:translateY(-3px);border-color:var(--purple);box-shadow:0 10px 25px rgba(168,85,247,0.2);}
.export-btn-icon{font-size:2rem;}
.export-btn-label{font-weight:600;}
.export-btn-sub{font-size:0.78rem;color:var(--text-sub);}

/* ============ TOAST ============ */
.toast{position:fixed;bottom:2rem;left:50%;transform:translateX(-50%) translateY(100px);background:linear-gradient(135deg,var(--purple-dark),var(--rose));color:white;padding:0.8rem 1.4rem;border-radius:50px;font-family:'Tajawal',sans-serif;font-size:0.97rem;font-weight:500;z-index:1000;box-shadow:0 10px 30px rgba(168,85,247,0.4);transition:transform 0.4s cubic-bezier(0.175,0.885,0.32,1.275);white-space:nowrap;}
.toast.show{transform:translateX(-50%) translateY(0);}

/* ============ MODAL ============ */
.modal-overlay{position:fixed;inset:0;background:rgba(0,0,0,0.88);backdrop-filter:blur(12px);z-index:500;display:none;align-items:center;justify-content:center;padding:2rem;}
.modal-overlay.open{display:flex;}
.modal-box{background:var(--bg-card);border:1px solid var(--border);border-radius:20px;max-width:90vw;max-height:90vh;overflow:auto;padding:1.5rem;position:relative;}
.modal-img-content{position:relative;}
.modal-img-content img{max-width:100%;max-height:80vh;border-radius:12px;object-fit:contain;}
.modal-close-btn{position:absolute;top:-12px;right:-12px;background:var(--rose);border:none;border-radius:50%;width:32px;height:32px;color:white;font-size:1rem;cursor:pointer;display:flex;align-items:center;justify-content:center;box-shadow:0 4px 15px rgba(255,107,157,0.5);transition:all 0.2s;}
.modal-close-btn:hover{transform:scale(1.1);}
.modal-nav-btn{position:absolute;top:50%;transform:translateY(-50%);background:rgba(0,0,0,0.6);border:none;border-radius:50%;width:38px;height:38px;color:white;font-size:1.2rem;cursor:pointer;display:flex;align-items:center;justify-content:center;transition:all 0.2s;}
.modal-nav-btn:hover{background:rgba(168,85,247,0.7);}
.modal-nav-btn.prev{right:-18px;}
.modal-nav-btn.next{left:-18px;}

/* ============ SECTION TITLE ============ */
.section-title{font-size:1.3rem;font-weight:700;margin-bottom:1rem;display:flex;align-items:center;gap:0.5rem;}

/* ============ RESPONSIVE ============ */
@media(max-width:640px){h1{font-size:1.9rem;}.form-grid{grid-template-columns:1fr;}.moments-grid{grid-template-columns:1fr;}.tabs{flex-wrap:wrap;}.top-bar-logo{font-size:1.1rem;}}

/* ============ SCROLLBAR ============ */
::-webkit-scrollbar{width:7px;}
::-webkit-scrollbar-track{background:rgba(255,255,255,0.03);}
::-webkit-scrollbar-thumb{background:linear-gradient(var(--purple),var(--rose));border-radius:4px;}

/* ============ PRINT / PDF ============ */
@media print{
  .top-bar,.tabs,.filters-bar,.btn-submit,.card-actions,.photo-upload-area,.particles,body::before{display:none!important;}
  body{background:white;color:black;}
  .moment-card{break-inside:avoid;border:1px solid #ddd;margin-bottom:1rem;}
}
</style>
</head>
<body>

<!-- Particles -->
<div class="particles" id="particles"></div>

<!-- Image Modal -->
<div class="modal-overlay" id="imageModal">
  <div class="modal-img-content" id="modalImgWrap">
    <button class="modal-close-btn" onclick="closeModal()">✕</button>
    <img id="modalImage" src="" alt=""/>
    <button class="modal-nav-btn prev" id="modalNext" onclick="modalNav(1)">›</button>
    <button class="modal-nav-btn next" id="modalPrev" onclick="modalNav(-1)">‹</button>
  </div>
</div>

<!-- Toast -->
<div class="toast" id="toast"></div>

<!-- Top Bar -->
<div class="top-bar">
  <div class="top-bar-logo">✨ مذكرة اللحظات</div>
  <div class="top-bar-actions">
    <button class="icon-btn" onclick="toggleTheme()" id="themeBtn" title="تغيير المظهر">🌙 مظهر</button>
    <button class="icon-btn" onclick="quickExport()" title="تصدير PDF">📤 تصدير</button>
  </div>
</div>

<!-- Header -->
<header>
  <span class="header-icon">✨</span>
  <h1>مذكرة اللحظات السعيدة</h1>
  <p class="subtitle">سجّل كل لحظة جميلة واحتفظ بها إلى الأبد <span style="font-size:1rem">🎁</span></p>
</header>

<div class="container">

  <!-- Stats -->
  <div class="stats-bar">
    <div class="stat-chip">📝 <span>اللحظات: <strong id="totalCount">0</strong></span></div>
    <div class="stat-chip">⭐ <span>المفضلة: <strong id="favCount">0</strong></span></div>
    <div class="stat-chip">📸 <span>الصور: <strong id="photoCount">0</strong></span></div>
    <div class="stat-chip">📅 <span>آخر تسجيل: <strong id="lastDate">—</strong></span></div>
  </div>

  <!-- Tabs -->
  <div class="tabs">
    <button class="tab-btn active" onclick="showTab('add',this)" id="tabAdd">✍️ إضافة لحظة</button>
    <button class="tab-btn" onclick="showTab('moments',this)" id="tabMoments">🌟 لحظاتي</button>
    <button class="tab-btn" onclick="showTab('calendar',this)" id="tabCalendar">🗓️ التقويم</button>
    <button class="tab-btn" onclick="showTab('reminders',this)" id="tabReminders">🔔 التذكيرات</button>
    <button class="tab-btn" onclick="showTab('export',this)" id="tabExport">📤 تصدير</button>
  </div>

  <!-- TAB: ADD -->
  <div class="tab-content active" id="tab-add">
    <div class="form-card">
      <div class="form-title">✍️ سجّل لحظتك السعيدة</div>
      <div class="form-grid">
        <div class="form-group full-width">
          <label for="momentTitle">📌 عنوان اللحظة</label>
          <input type="text" id="momentTitle" placeholder="مثال: رحلة العائلة إلى البحر..."/>
        </div>
        <div class="form-group">
          <label for="momentDate">📅 التاريخ</label>
          <input type="date" id="momentDate"/>
        </div>
        <div class="form-group">
          <label for="momentCategory">🏷️ الفئة</label>
          <select id="momentCategory">
            <option value="family">👨‍👩‍👧 عائلة</option>
            <option value="friends">👫 أصدقاء</option>
            <option value="achievement">🏆 إنجاز</option>
            <option value="nature">🌿 طبيعة</option>
            <option value="travel">✈️ سفر</option>
            <option value="other">💫 أخرى</option>
          </select>
        </div>
        <div class="form-group full-width">
          <label>😊 كيف كان شعورك؟</label>
          <div class="mood-selector" id="moodSelector">
            <button class="mood-btn" data-mood="سعيد جداً" onclick="selectMood(this)">😄 <span class="mood-label">سعيد جداً</span></button>
            <button class="mood-btn" data-mood="ممتنّ" onclick="selectMood(this)">🥹 <span class="mood-label">ممتنّ</span></button>
            <button class="mood-btn" data-mood="فخور" onclick="selectMood(this)">🤩 <span class="mood-label">فخور</span></button>
            <button class="mood-btn" data-mood="مرتاح" onclick="selectMood(this)">😌 <span class="mood-label">مرتاح</span></button>
            <button class="mood-btn" data-mood="محبّ" onclick="selectMood(this)">🥰 <span class="mood-label">محبّ</span></button>
            <button class="mood-btn" data-mood="مبتهج" onclick="selectMood(this)">🎉 <span class="mood-label">مبتهج</span></button>
            <button class="mood-btn" data-mood="مندهش" onclick="selectMood(this)">😮 <span class="mood-label">مندهش</span></button>
            <button class="mood-btn" data-mood="مسالم" onclick="selectMood(this)">☮️ <span class="mood-label">مسالم</span></button>
          </div>
        </div>
        <div class="form-group full-width">
          <label for="momentDesc">💬 وصف اللحظة</label>
          <textarea id="momentDesc" placeholder="صِف هذه اللحظة الجميلة... ماذا حدث؟ من كان معك؟ ما الذي جعلها مميزة؟"></textarea>
        </div>
        <div class="form-group full-width">
          <label>📸 أضف صوراً</label>
          <div class="photo-upload-area" id="uploadArea"
               ondragover="handleDragOver(event)" ondragleave="handleDragLeave(event)" ondrop="handleDrop(event)">
            <input type="file" id="photoInput" accept="image/*" multiple onchange="handleFiles(this.files)"/>
            <div class="upload-icon">📂</div>
            <div class="upload-text"><strong>اضغط لاختيار صور</strong> أو اسحبها وأفلتها هنا<br/><small style="color:var(--text-sub)">PNG, JPG, GIF مدعومة</small></div>
          </div>
          <div class="preview-grid" id="previewGrid"></div>
        </div>
      </div>
      <button class="btn-submit" onclick="saveMoment()">✨ حفظ اللحظة السعيدة</button>
    </div>

    <!-- Memories shown below form -->
    <div style="margin-top:2rem;">
      <div class="section-title">🎁 ذكرياتي السعيدة</div>
      <div class="filters-bar" id="filterBarInline">
        <input class="search-box" id="searchBox" type="text" placeholder="🔍 ابحث في لحظاتك..." oninput="renderMoments()"/>
        <button class="filter-btn active" onclick="setFilter('all',this)">الكل</button>
        <button class="filter-btn" onclick="setFilter('family',this)">👨‍👩‍👧 عائلة</button>
        <button class="filter-btn" onclick="setFilter('friends',this)">👫 أصدقاء</button>
        <button class="filter-btn" onclick="setFilter('achievement',this)">🏆 إنجاز</button>
        <button class="filter-btn" onclick="setFilter('nature',this)">🌿 طبيعة</button>
        <button class="filter-btn" onclick="setFilter('travel',this)">✈️ سفر</button>
        <button class="filter-btn" onclick="setFilter('favorites',this)">⭐ المفضلة</button>
      </div>
      <div class="moments-grid" id="momentsGrid"></div>
    </div>
  </div>

  <!-- TAB: MOMENTS -->
  <div class="tab-content" id="tab-moments">
    <div class="section-title">🌟 لحظاتي السعيدة</div>
    <div class="filters-bar">
      <input class="search-box" id="searchBox2" type="text" placeholder="🔍 ابحث في لحظاتك..." oninput="renderMoments2()"/>
      <button class="filter-btn active" onclick="setFilter2('all',this)">الكل</button>
      <button class="filter-btn" onclick="setFilter2('family',this)">👨‍👩‍👧 عائلة</button>
      <button class="filter-btn" onclick="setFilter2('friends',this)">👫 أصدقاء</button>
      <button class="filter-btn" onclick="setFilter2('achievement',this)">🏆 إنجاز</button>
      <button class="filter-btn" onclick="setFilter2('nature',this)">🌿 طبيعة</button>
      <button class="filter-btn" onclick="setFilter2('travel',this)">✈️ سفر</button>
      <button class="filter-btn" onclick="setFilter2('favorites',this)">⭐ المفضلة</button>
    </div>
    <div class="moments-grid" id="momentsGrid2"></div>
  </div>

  <!-- TAB: CALENDAR -->
  <div class="tab-content" id="tab-calendar">
    <div class="calendar-wrap">
      <div class="cal-header">
        <button class="cal-nav" onclick="calNav(-1)">›</button>
        <div class="cal-title" id="calTitle"></div>
        <button class="cal-nav" onclick="calNav(1)">‹</button>
      </div>
      <div class="cal-weekdays">
        <div class="cal-weekday">أحد</div>
        <div class="cal-weekday">إثنين</div>
        <div class="cal-weekday">ثلاثاء</div>
        <div class="cal-weekday">أربعاء</div>
        <div class="cal-weekday">خميس</div>
        <div class="cal-weekday">جمعة</div>
        <div class="cal-weekday">سبت</div>
      </div>
      <div class="cal-days" id="calDays"></div>
      <div class="cal-events" id="calEvents"></div>
    </div>
  </div>

  <!-- TAB: REMINDERS -->
  <div class="tab-content" id="tab-reminders">
    <div class="reminder-section">
      <div class="reminder-header">
        <div class="reminder-title">🔔 تذكيرات يومية</div>
        <label class="toggle-switch">
          <input type="checkbox" id="reminderToggle" onchange="toggleReminder()"/>
          <span class="toggle-slider"></span>
        </label>
      </div>
      <div id="reminderBody">
        <div class="notif-perms" id="notifStatus"></div>
        <div class="reminder-form" id="reminderForm" style="margin-top:1rem;">
          <div class="reminder-row">
            <label>🕐 وقت التذكير اليومي:</label>
            <input type="time" class="reminder-input" id="reminderTime" value="20:00"/>
          </div>
          <div class="reminder-row">
            <label>💬 رسالة التذكير:</label>
            <input type="text" class="reminder-input" id="reminderText" value="هل سجّلت لحظة سعيدة اليوم؟ 🌟" style="flex:1;min-width:200px;direction:rtl;"/>
          </div>
          <button class="btn-submit" style="margin-top:0.5rem" onclick="saveReminder()">💾 حفظ إعدادات التذكير</button>
        </div>
        <div style="margin-top:1.2rem;padding:1rem;background:rgba(255,255,255,0.04);border-radius:12px;border:1px solid var(--border);">
          <div style="font-size:0.9rem;font-weight:600;margin-bottom:0.5rem;">📋 ملاحظات مهمة:</div>
          <ul style="font-size:0.85rem;color:var(--text-sub);list-style:none;display:flex;flex-direction:column;gap:0.35rem;">
            <li>• يجب أن يكون المتصفح مفتوحاً أو في الخلفية</li>
            <li>• اسمح بالإشعارات عند الطلب لتفعيل التذكيرات</li>
            <li>• التذكيرات تعمل بتوقيت جهازك المحلي</li>
            <li>• يتم التحقق من الوقت كل دقيقة</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <!-- TAB: EXPORT -->
  <div class="tab-content" id="tab-export">
    <div class="export-section">
      <div class="export-title">📤 تصدير اللحظات</div>
      <div class="export-options">
        <button class="export-btn" onclick="exportPDF()">
          <div class="export-btn-icon">📄</div>
          <div class="export-btn-label">تصدير PDF</div>
          <div class="export-btn-sub">ملف PDF بكل اللحظات</div>
        </button>
        <button class="export-btn" onclick="exportJSON()">
          <div class="export-btn-icon">💾</div>
          <div class="export-btn-label">نسخة احتياطية</div>
          <div class="export-btn-sub">حفظ البيانات JSON</div>
        </button>
        <button class="export-btn" onclick="importJSON()">
          <div class="export-btn-icon">📥</div>
          <div class="export-btn-label">استيراد بيانات</div>
          <div class="export-btn-sub">استعادة نسخة احتياطية</div>
        </button>
        <button class="export-btn" onclick="exportText()">
          <div class="export-btn-icon">📝</div>
          <div class="export-btn-label">تصدير نص</div>
          <div class="export-btn-sub">ملف نصي للطباعة</div>
        </button>
        <button class="export-btn" onclick="printMoments()">
          <div class="export-btn-icon">🖨️</div>
          <div class="export-btn-label">طباعة</div>
          <div class="export-btn-sub">طباعة مباشرة</div>
        </button>
        <button class="export-btn" onclick="shareMoments()">
          <div class="export-btn-icon">📱</div>
          <div class="export-btn-label">مشاركة</div>
          <div class="export-btn-sub">مشاركة الملخص</div>
        </button>
      </div>
    </div>
    <div class="export-section">
      <div class="export-title">📊 إحصائيات تفصيلية</div>
      <div id="statsDetail"></div>
    </div>
    <input type="file" id="importFile" accept=".json" style="display:none" onchange="processImport(this)"/>
  </div>

</div><!-- /container -->

<script>
/* ============================================================
   STATE
   ============================================================ */
let moments = JSON.parse(localStorage.getItem('happyMoments') || '[]');
let selectedMood = '';
let selectedImages = [];
let currentFilter = 'all';
let isLightMode = localStorage.getItem('lightMode') === 'true';
let calYear = new Date().getFullYear();
let calMonth = new Date().getMonth();
let selectedCalDay = null;
let modalImages = [];
let modalIndex = 0;
let reminderInterval = null;

const MOOD_EMOJI = {'سعيد جداً':'😄','ممتنّ':'🥹','فخور':'🤩','مرتاح':'😌','محبّ':'🥰','مبتهج':'🎉','مندهش':'😮','مسالم':'☮️'};
const CAT = {family:{l:'عائلة',c:'category-family'},friends:{l:'أصدقاء',c:'category-friends'},achievement:{l:'إنجاز',c:'category-achievement'},nature:{l:'طبيعة',c:'category-nature'},travel:{l:'سفر',c:'category-travel'},other:{l:'أخرى',c:'category-other'}};

/* ============================================================
   INIT
   ============================================================ */
document.getElementById('momentDate').valueAsDate = new Date();
if(isLightMode){ document.body.classList.add('light'); document.getElementById('themeBtn').textContent='☀️ مظهر'; }
createParticles();
renderMoments();
renderMoments2();
updateStats();
renderCalendar();
initReminder();
renderStatsDetail();

/* ============================================================
   THEME
   ============================================================ */
function toggleTheme(){
  isLightMode=!isLightMode;
  document.body.classList.toggle('light',isLightMode);
  document.getElementById('themeBtn').textContent=isLightMode?'☀️ مظهر':'🌙 مظهر';
  localStorage.setItem('lightMode',isLightMode);
  showToast(isLightMode?'☀️ المظهر النهاري':'🌙 المظهر الليلي');
}

/* ============================================================
   TABS
   ============================================================ */
function showTab(id,btn){
  document.querySelectorAll('.tab-content').forEach(t=>t.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b=>b.classList.remove('active'));
  document.getElementById('tab-'+id).classList.add('active');
  btn.classList.add('active');
  if(id==='calendar') renderCalendar();
  if(id==='export') renderStatsDetail();
}

/* ============================================================
   MOOD
   ============================================================ */
function selectMood(btn){
  document.querySelectorAll('.mood-btn').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
  selectedMood=btn.dataset.mood;
}

/* ============================================================
   FILE HANDLING
   ============================================================ */
function handleFiles(files){
  Array.from(files).forEach(f=>{
    if(!f.type.startsWith('image/'))return;
    const r=new FileReader();
    r.onload=e=>{selectedImages.push({dataUrl:e.target.result,name:f.name});renderPreview();};
    r.readAsDataURL(f);
  });
}
function renderPreview(){
  const g=document.getElementById('previewGrid');
  g.innerHTML='';
  selectedImages.forEach((img,i)=>{
    const d=document.createElement('div');
    d.className='preview-item';
    d.innerHTML=`<img src="${img.dataUrl}" alt="${img.name}"/><button class="remove-img" onclick="removeImage(${i})">✕</button>`;
    g.appendChild(d);
  });
}
function removeImage(i){selectedImages.splice(i,1);renderPreview();}
function handleDragOver(e){e.preventDefault();document.getElementById('uploadArea').classList.add('drag-over');}
function handleDragLeave(){document.getElementById('uploadArea').classList.remove('drag-over');}
function handleDrop(e){e.preventDefault();document.getElementById('uploadArea').classList.remove('drag-over');handleFiles(e.dataTransfer.files);}

/* ============================================================
   SAVE MOMENT
   ============================================================ */
function saveMoment(){
  const title=document.getElementById('momentTitle').value.trim();
  const date=document.getElementById('momentDate').value;
  const category=document.getElementById('momentCategory').value;
  const desc=document.getElementById('momentDesc').value.trim();
  if(!title){showToast('⚠️ يرجى إدخال عنوان');return;}
  if(!date){showToast('⚠️ يرجى اختيار التاريخ');return;}
  const m={id:Date.now(),title,date,category,mood:selectedMood||'سعيد جداً',desc,images:selectedImages.map(i=>i.dataUrl),favorite:false,createdAt:new Date().toISOString()};
  moments.unshift(m);
  saveToStorage();resetForm();renderMoments();renderMoments2();updateStats();renderCalendar();
  showToast('✨ تم حفظ لحظتك السعيدة!');
  // scroll to memories section
  setTimeout(()=>{ const g=document.getElementById('momentsGrid'); if(g)g.scrollIntoView({behavior:'smooth',block:'start'}); },300);
}
function resetForm(){
  document.getElementById('momentTitle').value='';
  document.getElementById('momentDate').valueAsDate=new Date();
  document.getElementById('momentDesc').value='';
  document.getElementById('momentCategory').value='family';
  document.querySelectorAll('.mood-btn').forEach(b=>b.classList.remove('active'));
  selectedMood='';selectedImages=[];
  document.getElementById('previewGrid').innerHTML='';
  document.getElementById('photoInput').value='';
}
function saveToStorage(){
  try{localStorage.setItem('happyMoments',JSON.stringify(moments));}
  catch(e){moments=moments.slice(0,60);localStorage.setItem('happyMoments',JSON.stringify(moments));}
}

/* ============================================================
   RENDER MOMENTS
   ============================================================ */
function renderMoments(){
  const grid=document.getElementById('momentsGrid');
  const s=(document.getElementById('searchBox')||{}).value||'';
  const search=s.trim().toLowerCase();
  let filtered=moments.filter(m=>{
    const ms=!search||m.title.toLowerCase().includes(search)||m.desc.toLowerCase().includes(search);
    const mf=currentFilter==='all'||(currentFilter==='favorites'&&m.favorite)||m.category===currentFilter;
    return ms&&mf;
  });
  if(!filtered.length){
    grid.innerHTML=`<div class="empty-state"><div class="empty-icon" style="font-size:3.5rem">🎁</div><div class="empty-title">لا توجد لحظات بعد</div><div class="empty-subtitle">ابدأ بتسجيل أول لحظة سعيدة!</div></div>`;
    return;
  }
  grid.innerHTML=filtered.map(m=>buildCard(m)).join('');
}
function buildCard(m){
  const cat=CAT[m.category]||CAT.other;
  const emoji=MOOD_EMOJI[m.mood]||'😊';
  const d=m.date?new Date(m.date+'T12:00:00').toLocaleDateString('ar-EG',{year:'numeric',month:'long',day:'numeric'}):'';
  const imgHtml=m.images&&m.images.length
    ?`<div class="card-gallery"><img src="${m.images[0]}" alt="صورة" onclick="openGallery(${m.id},0)"/>${m.images.length>1?`<span class="gallery-count">+${m.images.length-1} صور</span>`:''}</div>`
    :`<div class="no-image-banner">${emoji}</div>`;
  return `<div class="moment-card ${m.favorite?'is-favorite':''}" id="card-${m.id}">
    ${imgHtml}
    <div class="card-content">
      <div class="card-header"><div class="card-title">${esc(m.title)}</div><div class="card-mood">${emoji}</div></div>
      <div class="card-meta"><span class="meta-tag">📅 ${d}</span><span class="meta-tag">😊 ${esc(m.mood)}</span></div>
      <span class="card-category ${cat.c}">${cat.l}</span>
      ${m.desc?`<p class="card-desc">${esc(m.desc)}</p>`:''}
      <div class="card-actions">
        <button class="action-btn favorite" onclick="toggleFav(${m.id})">${m.favorite?'⭐':'☆'} ${m.favorite?'مفضّلة':'تفضيل'}</button>
        ${m.images&&m.images.length>1?`<button class="action-btn" onclick="openGallery(${m.id},0)">🖼️ الصور</button>`:''}
        <button class="action-btn delete" onclick="deleteMoment(${m.id})">🗑️ حذف</button>
      </div>
    </div>
  </div>`;
}
function esc(s){const d=document.createElement('div');d.textContent=s||'';return d.innerHTML;}

/* ============================================================
   FILTER
   ============================================================ */
function setFilter(f,btn){
  currentFilter=f;
  document.querySelectorAll('.filter-btn').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
  renderMoments();
}

let currentFilter2 = 'all';
function setFilter2(f,btn){
  currentFilter2=f;
  document.querySelectorAll('#tab-moments .filter-btn').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
  renderMoments2();
}
function renderMoments2(){
  const grid=document.getElementById('momentsGrid2');
  if(!grid)return;
  const s=(document.getElementById('searchBox2')||{}).value||'';
  const search=s.trim().toLowerCase();
  let filtered=moments.filter(m=>{
    const ms=!search||m.title.toLowerCase().includes(search)||(m.desc||'').toLowerCase().includes(search);
    const mf=currentFilter2==='all'||(currentFilter2==='favorites'&&m.favorite)||m.category===currentFilter2;
    return ms&&mf;
  });
  if(!filtered.length){
    grid.innerHTML=`<div class="empty-state"><div class="empty-icon" style="font-size:3.5rem">🎁</div><div class="empty-title">لا توجد لحظات بعد</div><div class="empty-subtitle">ابدأ بتسجيل أول لحظة سعيدة!</div></div>`;
    return;
  }
  grid.innerHTML=filtered.map(m=>buildCard(m)).join('');
}

/* ============================================================
   ACTIONS
   ============================================================ */
function toggleFav(id){
  const m=moments.find(m=>m.id===id);
  if(m){m.favorite=!m.favorite;saveToStorage();renderMoments();renderMoments2();updateStats();showToast(m.favorite?'⭐ أضيفت للمفضلة!':'☆ أُزيلت من المفضلة');}
}
function deleteMoment(id){
  if(!confirm('هل تريد حذف هذه اللحظة نهائياً؟'))return;
  moments=moments.filter(m=>m.id!==id);saveToStorage();renderMoments();renderMoments2();updateStats();renderCalendar();showToast('🗑️ تم الحذف');
}

/* ============================================================
   STATS
   ============================================================ */
function updateStats(){
  document.getElementById('totalCount').textContent=moments.length;
  document.getElementById('favCount').textContent=moments.filter(m=>m.favorite).length;
  document.getElementById('photoCount').textContent=moments.reduce((a,m)=>a+(m.images?m.images.length:0),0);
  if(moments.length){
    const latest=[...moments].sort((a,b)=>new Date(b.createdAt)-new Date(a.createdAt))[0];
    const d=new Date(latest.date+'T12:00:00');
    document.getElementById('lastDate').textContent=d.toLocaleDateString('ar-EG',{month:'short',day:'numeric'});
  } else document.getElementById('lastDate').textContent='—';
}
function renderStatsDetail(){
  const el=document.getElementById('statsDetail');
  if(!el)return;
  const cats={family:0,friends:0,achievement:0,nature:0,travel:0,other:0};
  const moods={};
  moments.forEach(m=>{
    if(cats[m.category]!==undefined)cats[m.category]++;
    else cats.other++;
    moods[m.mood]=(moods[m.mood]||0)+1;
  });
  const catRows=Object.entries(cats).filter(([,v])=>v>0).map(([k,v])=>`<tr><td style="padding:6px 10px">${CAT[k]?.l||k}</td><td style="padding:6px 10px;text-align:left"><strong>${v}</strong></td></tr>`).join('');
  const moodRows=Object.entries(moods).sort((a,b)=>b[1]-a[1]).slice(0,5).map(([k,v])=>`<tr><td style="padding:6px 10px">${MOOD_EMOJI[k]||''} ${k}</td><td style="padding:6px 10px;text-align:left"><strong>${v}</strong></td></tr>`).join('');
  el.innerHTML=`
    <div style="display:grid;grid-template-columns:1fr 1fr;gap:1rem">
      <div>
        <div style="font-size:0.9rem;font-weight:600;margin-bottom:0.6rem;color:var(--text-sub)">حسب الفئة</div>
        <table style="width:100%;border-collapse:collapse;font-size:0.9rem">${catRows||'<tr><td style="padding:6px 10px;color:var(--text-sub)">لا يوجد بيانات</td></tr>'}</table>
      </div>
      <div>
        <div style="font-size:0.9rem;font-weight:600;margin-bottom:0.6rem;color:var(--text-sub)">أكثر المشاعر</div>
        <table style="width:100%;border-collapse:collapse;font-size:0.9rem">${moodRows||'<tr><td style="padding:6px 10px;color:var(--text-sub)">لا يوجد بيانات</td></tr>'}</table>
      </div>
    </div>
    <div style="margin-top:1rem;padding:0.8rem 1rem;background:rgba(168,85,247,0.08);border-radius:12px;border:1px solid rgba(168,85,247,0.2);font-size:0.9rem">
      📊 إجمالي: <strong>${moments.length}</strong> لحظة | ⭐ مفضلة: <strong>${moments.filter(m=>m.favorite).length}</strong> | 📸 صور: <strong>${moments.reduce((a,m)=>a+(m.images?m.images.length:0),0)}</strong>
    </div>`;
}

/* ============================================================
   IMAGE GALLERY MODAL
   ============================================================ */
function openGallery(id,idx){
  const m=moments.find(m=>m.id===id);
  if(!m||!m.images||!m.images.length)return;
  modalImages=m.images;
  modalIndex=idx||0;
  showModalImg();
}
function showModalImg(){
  document.getElementById('modalImage').src=modalImages[modalIndex];
  document.getElementById('imageModal').classList.add('open');
  document.getElementById('modalPrev').style.display=modalImages.length>1?'flex':'none';
  document.getElementById('modalNext').style.display=modalImages.length>1?'flex':'none';
}
function modalNav(dir){
  modalIndex=(modalIndex+dir+modalImages.length)%modalImages.length;
  showModalImg();
}
function closeModal(){document.getElementById('imageModal').classList.remove('open');}
document.getElementById('imageModal').addEventListener('click',function(e){if(e.target===this)closeModal();});

/* ============================================================
   CALENDAR
   ============================================================ */
const AR_MONTHS=['يناير','فبراير','مارس','أبريل','مايو','يونيو','يوليو','أغسطس','سبتمبر','أكتوبر','نوفمبر','ديسمبر'];
function calNav(dir){
  calMonth+=dir;
  if(calMonth>11){calMonth=0;calYear++;}
  if(calMonth<0){calMonth=11;calYear--;}
  renderCalendar();
}
function renderCalendar(){
  document.getElementById('calTitle').textContent=`${AR_MONTHS[calMonth]} ${calYear}`;
  const first=new Date(calYear,calMonth,1).getDay();
  const days=new Date(calYear,calMonth+1,0).getDate();
  const today=new Date();
  const todayStr=`${today.getFullYear()}-${String(today.getMonth()+1).padStart(2,'0')}-${String(today.getDate()).padStart(2,'0')}`;
  const momentDates=new Set(moments.map(m=>m.date));
  let html='';
  for(let i=0;i<first;i++)html+=`<div class="cal-day empty"></div>`;
  for(let d=1;d<=days;d++){
    const ds=`${calYear}-${String(calMonth+1).padStart(2,'0')}-${String(d).padStart(2,'0')}`;
    const isT=ds===todayStr,isM=momentDates.has(ds),isSel=ds===selectedCalDay;
    html+=`<div class="cal-day ${isT?'today':''} ${isM?'has-moment':''} ${isSel?'selected':''}" onclick="selectCalDay('${ds}')">${d}</div>`;
  }
  document.getElementById('calDays').innerHTML=html;
  renderCalEvents();
}
function selectCalDay(ds){
  selectedCalDay=ds;
  renderCalendar();
}
function renderCalEvents(){
  const el=document.getElementById('calEvents');
  const toShow=selectedCalDay
    ?moments.filter(m=>m.date===selectedCalDay)
    :moments.filter(m=>m.date&&m.date.startsWith(`${calYear}-${String(calMonth+1).padStart(2,'0')}`));
  if(!toShow.length){el.innerHTML=selectedCalDay?`<div style="text-align:center;color:var(--text-sub);padding:1rem">لا توجد لحظات في هذا اليوم</div>`:`<div style="text-align:center;color:var(--text-sub);padding:1rem">اضغط على يوم لعرض لحظاته</div>`;return;}
  el.innerHTML=toShow.map(m=>{
    const emoji=MOOD_EMOJI[m.mood]||'😊';
    const d=new Date(m.date+'T12:00:00').toLocaleDateString('ar-EG',{weekday:'long',month:'long',day:'numeric'});
    return `<div class="cal-event-item" onclick="goToMoment(${m.id})">
      <div class="cal-event-emoji">${emoji}</div>
      <div class="cal-event-info"><div class="cal-event-title">${esc(m.title)}</div><div class="cal-event-date">📅 ${d}</div></div>
      ${m.favorite?'<span style="color:var(--gold)">⭐</span>':''}
    </div>`;
  }).join('');
}
function goToMoment(id){
  showTab('moments',document.getElementById('tabMoments'));
  setTimeout(()=>{
    const el=document.getElementById('card-'+id);
    if(el){el.scrollIntoView({behavior:'smooth',block:'center'});el.style.outline='2px solid var(--purple)';setTimeout(()=>el.style.outline='',2000);}
  },200);
}

/* ============================================================
   REMINDERS
   ============================================================ */
function initReminder(){
  const saved=JSON.parse(localStorage.getItem('reminderSettings')||'{}');
  if(saved.time)document.getElementById('reminderTime').value=saved.time;
  if(saved.text)document.getElementById('reminderText').value=saved.text;
  const enabled=saved.enabled||false;
  document.getElementById('reminderToggle').checked=enabled;
  updateNotifStatus();
  if(enabled)startReminderInterval();
}
function toggleReminder(){
  const enabled=document.getElementById('reminderToggle').checked;
  if(enabled){
    if(!('Notification' in window)){showNotifStatus('❌ متصفحك لا يدعم الإشعارات','error');document.getElementById('reminderToggle').checked=false;return;}
    Notification.requestPermission().then(p=>{
      if(p==='granted'){saveReminderSettings(true);startReminderInterval();showNotifStatus('✅ تم تفعيل التذكيرات بنجاح!','success');showToast('🔔 تم تفعيل التذكيرات!');}
      else{showNotifStatus('⚠️ يرجى السماح بالإشعارات من إعدادات المتصفح','warning');document.getElementById('reminderToggle').checked=false;}
    });
  } else {
    stopReminderInterval();saveReminderSettings(false);showNotifStatus('🔕 تم إيقاف التذكيرات','warning');showToast('🔕 تم إيقاف التذكيرات');
  }
}
function saveReminder(){
  const enabled=document.getElementById('reminderToggle').checked;
  saveReminderSettings(enabled);
  if(enabled){stopReminderInterval();startReminderInterval();}
  showToast('💾 تم حفظ إعدادات التذكير!');
}
function saveReminderSettings(enabled){
  const s={enabled,time:document.getElementById('reminderTime').value,text:document.getElementById('reminderText').value};
  localStorage.setItem('reminderSettings',JSON.stringify(s));
}
function startReminderInterval(){
  stopReminderInterval();
  reminderInterval=setInterval(checkReminder,60000);
  checkReminder();
}
function stopReminderInterval(){if(reminderInterval){clearInterval(reminderInterval);reminderInterval=null;}}
function checkReminder(){
  const s=JSON.parse(localStorage.getItem('reminderSettings')||'{}');
  if(!s.enabled||!s.time)return;
  const now=new Date();
  const [h,m]=s.time.split(':').map(Number);
  if(now.getHours()===h&&now.getMinutes()===m&&Notification.permission==='granted'){
    new Notification('مذكرة اللحظات السعيدة ✨',{body:s.text||'هل سجّلت لحظة سعيدة اليوم؟',icon:'data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><text y=".9em" font-size="90">✨</text></svg>'});
  }
}
function updateNotifStatus(){
  if(!('Notification' in window)){showNotifStatus('❌ متصفحك لا يدعم الإشعارات','error');return;}
  if(Notification.permission==='granted')showNotifStatus('✅ الإشعارات مفعّلة','success');
  else if(Notification.permission==='denied')showNotifStatus('❌ الإشعارات محظورة - اسمح بها من إعدادات المتصفح','error');
  else showNotifStatus('ℹ️ فعّل الزر أعلاه للسماح بالإشعارات','warning');
}
function showNotifStatus(msg,type){
  const el=document.getElementById('notifStatus');
  el.innerHTML=`<div class="reminder-msg ${type}">${msg}</div>`;
}

/* ============================================================
   EXPORT
   ============================================================ */
async function exportPDF(){
  if(!moments.length){showToast('⚠️ لا توجد لحظات لتصديرها');return;}
  showToast('⏳ جاري إنشاء PDF...');
  try{
    const {jsPDF}=window.jspdf;
    const doc=new jsPDF({orientation:'portrait',unit:'mm',format:'a4'});
    const pageW=210,margin=15,lineH=7;
    let y=margin;
    // Title page
    doc.setFontSize(22);doc.setTextColor(168,85,247);
    doc.text('Happy Moments Journal',pageW/2,y+10,{align:'center'});
    doc.setFontSize(12);doc.setTextColor(120,100,150);
    doc.text(`Total Moments: ${moments.length}  |  Favorites: ${moments.filter(m=>m.favorite).length}`,pageW/2,y+22,{align:'center'});
    doc.text(`Generated: ${new Date().toLocaleDateString('ar-EG')}`,pageW/2,y+30,{align:'center'});
    y+=45;doc.setDrawColor(168,85,247);doc.line(margin,y,pageW-margin,y);y+=10;
    for(const m of moments){
      if(y>265){doc.addPage();y=margin;}
      const d=m.date?new Date(m.date+'T12:00:00').toLocaleDateString('ar-EG',{year:'numeric',month:'long',day:'numeric'}):'';
      const emoji=MOOD_EMOJI[m.mood]||'😊';
      doc.setFontSize(13);doc.setTextColor(50,20,80);
      doc.text(`${emoji} ${m.title}`,pageW-margin,y,{align:'right'});y+=lineH;
      doc.setFontSize(9);doc.setTextColor(130,100,160);
      doc.text(`${d}  |  ${m.mood}  |  ${CAT[m.category]?.l||''}${m.favorite?' | ⭐':''}`,pageW-margin,y,{align:'right'});y+=lineH;
      if(m.desc){
        doc.setFontSize(10);doc.setTextColor(80,60,100);
        const lines=doc.splitTextToSize(m.desc,pageW-margin*2);
        lines.forEach(line=>{if(y>265){doc.addPage();y=margin;}doc.text(line,pageW-margin,y,{align:'right'});y+=5;});
        y+=2;
      }
      doc.setDrawColor(220,210,240);doc.line(margin,y,pageW-margin,y);y+=8;
    }
    doc.save(`moments_${new Date().toISOString().slice(0,10)}.pdf`);
    showToast('✅ تم تصدير PDF بنجاح!');
  }catch(e){console.error(e);showToast('❌ خطأ في إنشاء PDF - جرب التصدير النصي');}
}
function exportJSON(){
  const data=JSON.stringify({version:'2.0',exportDate:new Date().toISOString(),moments},null,2);
  download('moments_backup.json',data,'application/json');
  showToast('💾 تم حفظ النسخة الاحتياطية!');
}
function importJSON(){document.getElementById('importFile').click();}
function processImport(input){
  const f=input.files[0];if(!f)return;
  const r=new FileReader();
  r.onload=e=>{
    try{
      const data=JSON.parse(e.target.result);
      const imported=data.moments||data;
      if(!Array.isArray(imported))throw new Error('Invalid format');
      if(!confirm(`سيتم استيراد ${imported.length} لحظة. هل تريد الدمج مع البيانات الحالية؟`))return;
      const ids=new Set(moments.map(m=>m.id));
      imported.forEach(m=>{if(!ids.has(m.id))moments.push(m);});
      moments.sort((a,b)=>new Date(b.createdAt)-new Date(a.createdAt));
      saveToStorage();renderMoments();updateStats();renderCalendar();
      showToast(`✅ تم استيراد ${imported.length} لحظة!`);
    }catch(ex){showToast('❌ ملف غير صالح');}
  };
  r.readAsText(f);
  input.value='';
}
function exportText(){
  if(!moments.length){showToast('⚠️ لا توجد لحظات');return;}
  let txt=`مذكرة اللحظات السعيدة\n${'='.repeat(40)}\nالتاريخ: ${new Date().toLocaleDateString('ar-EG')}\nإجمالي اللحظات: ${moments.length}\n\n`;
  moments.forEach((m,i)=>{
    const d=m.date?new Date(m.date+'T12:00:00').toLocaleDateString('ar-EG',{year:'numeric',month:'long',day:'numeric'}):'';
    txt+=`${i+1}. ${m.title}\n`;
    txt+=`   📅 ${d} | 😊 ${m.mood} | 🏷️ ${CAT[m.category]?.l||''}${m.favorite?' | ⭐ مفضّلة':''}\n`;
    if(m.desc)txt+=`   ${m.desc}\n`;
    if(m.images?.length)txt+=`   📸 ${m.images.length} صورة\n`;
    txt+=`${'─'.repeat(40)}\n`;
  });
  download('moments.txt',txt,'text/plain;charset=utf-8');
  showToast('📝 تم تصدير الملف النصي!');
}
function printMoments(){window.print();}
function shareMoments(){
  const text=`✨ مذكرة اللحظاتي السعيدة\n🌟 ${moments.length} لحظة مسجّلة\n⭐ ${moments.filter(m=>m.favorite).length} في المفضلة\n\nأحدث اللحظات:\n`+moments.slice(0,3).map(m=>`• ${m.title}`).join('\n');
  if(navigator.share){navigator.share({title:'مذكرة اللحظات السعيدة',text});}
  else{navigator.clipboard.writeText(text).then(()=>showToast('📋 تم نسخ الملخص!'));}
}
function quickExport(){exportJSON();}
function download(filename,content,type){
  const a=document.createElement('a');
  a.href=URL.createObjectURL(new Blob([content],{type}));
  a.download=filename;a.click();
  URL.revokeObjectURL(a.href);
}

/* ============================================================
   TOAST
   ============================================================ */
function showToast(msg){
  const t=document.getElementById('toast');
  t.textContent=msg;t.classList.add('show');
  setTimeout(()=>t.classList.remove('show'),2800);
}

/* ============================================================
   PARTICLES
   ============================================================ */
function createParticles(){
  const c=document.getElementById('particles');
  const cols=['#a855f7','#ff6b9d','#f5c842','#38bdf8','#34d399'];
  for(let i=0;i<16;i++){
    const p=document.createElement('div');p.className='particle';
    const sz=Math.random()*5+3;
    p.style.cssText=`width:${sz}px;height:${sz}px;background:${cols[Math.floor(Math.random()*cols.length)]};left:${Math.random()*100}%;animation-duration:${Math.random()*14+9}s;animation-delay:${Math.random()*10}s;`;
    c.appendChild(p);
  }
}
</script>
</body>
</html>
