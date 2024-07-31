# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Perform two-stage inverse-variance individual participant data (IPD) meta-analysis Use ipd (ipdma) (bipd) With (In) R Software
install.packages("bipd")
library("bipd")
ipdma = read.csv("https://raw.githubusercontent.com/timbulwidodostp/ipdma/main/ipdma/ipdma.csv",sep = ";")
# Estimation Perform two-stage inverse-variance individual participant data (IPD) meta-analysis Use ipd (ipdma) (bipd) With (In) R Software
ipd <- with(ipdma, ipdma.model.onestage(y = y, study = studyid, treat = treat, X = cbind(z1, z2), response = "normal", shrinkage = "none"))
cat(ipd$code)
samples <- ipd.run(ipd, n.chains = 3, n.burnin = 500, n.iter = 5000)
samples <- samples[, -3]
summary(samples)
treatment.effect(ipd, samples, newpatient = c(1, 0.5))
# Perform two-stage inverse-variance individual participant data (IPD) meta-analysis Use ipd (ipdma) (bipd) With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished