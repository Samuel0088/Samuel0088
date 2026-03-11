import { useState, useEffect } from "react";

const README = () => {
  const [typedText, setTypedText] = useState("");
  const [lineIndex, setLineIndex] = useState(0);
  const [charIndex, setCharIndex] = useState(0);

  const lines = [
    "Desenvolvendo soluções do back ao front",
    "Apaixonado por tecnologia e inovação",
    "Buscando estágio em desenvolvimento",
  ];

  useEffect(() => {
    if (lineIndex >= lines.length) return;
    const currentLine = lines[lineIndex];
    if (charIndex < currentLine.length) {
      const t = setTimeout(() => {
        setTypedText((p) => p + currentLine[charIndex]);
        setCharIndex((p) => p + 1);
      }, 45);
      return () => clearTimeout(t);
    } else {
      const t = setTimeout(() => {
        setTypedText("");
        setCharIndex(0);
        setLineIndex((p) => (p + 1) % lines.length);
      }, 1800);
      return () => clearTimeout(t);
    }
  }, [charIndex, lineIndex]);

  const techs = [
    { name: "HTML5", color: "#E34F26", logo: "html5" },
    { name: "CSS3", color: "#1572B6", logo: "css3" },
    { name: "JavaScript", color: "#F7DF1E", textColor: "#000", logo: "javascript" },
    { name: "React", color: "#20232A", logo: "react", accent: "#61DAFB" },
    { name: "Bootstrap", color: "#563D7C", logo: "bootstrap" },
    { name: "PHP", color: "#777BB4", logo: "php" },
    { name: "Python", color: "#3776AB", logo: "python" },
    { name: "MySQL", color: "#005C84", logo: "mysql" },
  ];

  const contacts = [
    { name: "LinkedIn", color: "#0077B5", url: "https://www.linkedin.com/in/samuel-vieira-0b3420341/", icon: "💼" },
    { name: "GitHub", color: "#181717", url: "https://github.com/Samuel0088", icon: "🐙" },
    { name: "Portfólio", color: "#000000", url: "https://portfolio-samuelvieira.vercel.app/", icon: "🌐" },
    { name: "E-mail", color: "#0078D4", url: "mailto:samuel.vieirafreitas@outlook.com", icon: "✉️" },
  ];

  const experience = [
    "Modelagem de banco de dados (MySQL)",
    "Desenvolvimento Full Stack",
    "Integração de módulo de IA",
    "Autenticação e controle de acesso",
    "Gateway de pagamento",
    "Metodologias ágeis",
  ];

  return (
    <div style={{
      background: "#0d1117",
      minHeight: "100vh",
      fontFamily: "'Segoe UI', sans-serif",
      color: "#c9d1d9",
      padding: "0",
    }}>
      {/* Header */}
      <div style={{
        background: "linear-gradient(135deg, #0f0c29, #302b63, #24243e)",
        padding: "52px 32px 40px",
        textAlign: "center",
        position: "relative",
        overflow: "hidden",
      }}>
        <div style={{
          position: "absolute", inset: 0,
          background: "radial-gradient(ellipse at 60% 40%, rgba(167,139,250,0.15) 0%, transparent 70%)",
        }} />
        <h1 style={{
          fontSize: "clamp(32px, 6vw, 52px)",
          fontWeight: 800,
          color: "#fff",
          margin: "0 0 8px",
          letterSpacing: "-1px",
          position: "relative",
        }}>Samuel Vieira</h1>
        <p style={{ color: "#a78bfa", fontSize: "15px", margin: 0, letterSpacing: "1px", position: "relative" }}>
          System Development Student · Full Stack
        </p>
        {/* Wave */}
        <svg viewBox="0 0 1440 60" style={{ position: "absolute", bottom: -1, left: 0, width: "100%" }}>
          <path fill="#0d1117" d="M0,30 C360,60 1080,0 1440,30 L1440,60 L0,60 Z" />
        </svg>
      </div>

      {/* Typing */}
      <div style={{ textAlign: "center", padding: "28px 16px 8px" }}>
        <span style={{
          fontFamily: "'Fira Code', monospace",
          color: "#a78bfa",
          fontSize: "15px",
          background: "rgba(167,139,250,0.07)",
          border: "1px solid rgba(167,139,250,0.2)",
          borderRadius: "8px",
          padding: "8px 20px",
          display: "inline-block",
          minWidth: "320px",
        }}>
          {typedText}<span style={{ animation: "blink 1s step-end infinite", opacity: 1 }}>|</span>
        </span>
      </div>

      <style>{`@keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }`}</style>

      {/* Two columns */}
      <div style={{
        display: "grid",
        gridTemplateColumns: "repeat(auto-fit, minmax(280px, 1fr))",
        gap: "24px",
        padding: "32px 24px",
        maxWidth: "1000px",
        margin: "0 auto",
      }}>
        {/* About */}
        <div style={{ background: "#161b22", borderRadius: "16px", border: "1px solid #21262d", padding: "28px" }}>
          <h2 style={{ color: "#a78bfa", fontSize: "16px", marginTop: 0, marginBottom: "14px" }}>👤 Sobre mim</h2>
          <p style={{ fontSize: "14px", lineHeight: "1.7", color: "#8b949e", margin: "0 0 24px" }}>
            Estudante de <strong style={{ color: "#c9d1d9" }}>Desenvolvimento de Sistemas</strong> pelo programa <strong style={{ color: "#c9d1d9" }}>AMS (ETEC + FATEC)</strong>, com conclusão prevista para <strong style={{ color: "#c9d1d9" }}>2026</strong>.<br /><br />
            Foco em web full stack — do banco à interface. Busco estágio para crescer profissionalmente.
          </p>
          <h2 style={{ color: "#a78bfa", fontSize: "16px", marginBottom: "14px" }}>🔭 Experiência Prática</h2>
          <div style={{ background: "#0d1117", borderRadius: "10px", padding: "16px", fontFamily: "'Fira Code', monospace", fontSize: "13px" }}>
            {experience.map((item, i) => (
              <div key={i} style={{ color: "#8b949e", marginBottom: i < experience.length - 1 ? "8px" : 0 }}>
                <span style={{ color: "#a78bfa" }}>✦ </span>{item}
              </div>
            ))}
          </div>
        </div>

        {/* Stats */}
        <div style={{ background: "#161b22", borderRadius: "16px", border: "1px solid #21262d", padding: "28px" }}>
          <h2 style={{ color: "#a78bfa", fontSize: "16px", marginTop: 0, marginBottom: "16px" }}>📊 GitHub Stats</h2>
          <img
            src="https://github-readme-stats.vercel.app/api?username=Samuel0088&show_icons=true&theme=midnight-purple&hide_border=true&bg_color=0d1117&title_color=a78bfa&icon_color=a78bfa&text_color=c9d1d9"
            style={{ width: "100%", borderRadius: "10px", marginBottom: "12px" }}
            alt="GitHub Stats"
          />
          <img
            src="https://github-readme-stats.vercel.app/api/top-langs/?username=Samuel0088&layout=compact&theme=midnight-purple&hide_border=true&bg_color=0d1117&title_color=a78bfa&text_color=c9d1d9"
            style={{ width: "100%", borderRadius: "10px" }}
            alt="Top Langs"
          />
        </div>
      </div>

      {/* Stack */}
      <div style={{ maxWidth: "1000px", margin: "0 auto", padding: "0 24px 24px" }}>
        <div style={{ background: "#161b22", borderRadius: "16px", border: "1px solid #21262d", padding: "28px" }}>
          <h2 style={{ color: "#a78bfa", fontSize: "16px", marginTop: 0, marginBottom: "20px", textAlign: "center" }}>🛠️ Stack</h2>
          <div style={{ display: "flex", flexWrap: "wrap", gap: "10px", justifyContent: "center" }}>
            {techs.map((t) => (
              <span key={t.name} style={{
                background: t.color,
                color: t.textColor || "#fff",
                padding: "7px 16px",
                borderRadius: "8px",
                fontSize: "13px",
                fontWeight: 600,
                letterSpacing: "0.5px",
              }}>{t.name}</span>
            ))}
          </div>
        </div>
      </div>

      {/* Contacts */}
      <div style={{ maxWidth: "1000px", margin: "0 auto", padding: "0 24px 48px" }}>
        <div style={{ background: "#161b22", borderRadius: "16px", border: "1px solid #21262d", padding: "28px" }}>
          <h2 style={{ color: "#a78bfa", fontSize: "16px", marginTop: 0, marginBottom: "20px", textAlign: "center" }}>📬 Contato</h2>
          <div style={{ display: "flex", flexWrap: "wrap", gap: "12px", justifyContent: "center" }}>
            {contacts.map((c) => (
              <a key={c.name} href={c.url} target="_blank" rel="noreferrer" style={{
                background: c.color,
                color: "#fff",
                padding: "10px 22px",
                borderRadius: "10px",
                fontSize: "14px",
                fontWeight: 600,
                textDecoration: "none",
                display: "flex",
                alignItems: "center",
                gap: "8px",
              }}>{c.icon} {c.name}</a>
            ))}
          </div>
        </div>
      </div>

      {/* Footer */}
      <div style={{
        background: "linear-gradient(135deg, #0f0c29, #302b63, #24243e)",
        height: "80px",
        position: "relative",
        overflow: "hidden",
      }}>
        <svg viewBox="0 0 1440 80" style={{ position: "absolute", top: -1, left: 0, width: "100%" }}>
          <path fill="#0d1117" d="M0,40 C360,0 1080,70 1440,30 L1440,0 L0,0 Z" />
        </svg>
      </div>
    </div>
  );
};

export default README;
