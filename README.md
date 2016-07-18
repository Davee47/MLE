# MLE%Inputs
global Du Do TL TM TH 
Du = 1;
Do = 1;
TL = 100; TM = 100; TH = 100;
%Given variables from experiment. H/M/L are high/Medium/Low conditions
pH = 4; pM = 3; pL = 3;
cH = 2; cM = 2; cL = 2.25;
gH = 4; gM = 1; gL = 0;
mu = 100;
sigma = 30;
% Equations 
% HL is H for the low-profit condition, HH is H for the high profit 
% QDH is the Q for High profit case
HL = (pL-cL+Du+gL)/(pL+Du+Do+gL);
HM = (pM-cM+Du+gM)/(pM+Du+Do+gM);
HH = (pH-cH+Du+gH)/(pH+Du+Do+gH);
ZL = norminv (HL);
ZM = norminv (HM);
ZH = norminv (HH);
qDH = (mu+(ZH*sigma));
qDM = (mu+(ZM*sigma));
qDL = (mu+(ZL*sigma));
% Begin Density generation
B=zeros(696,1);
T=((A1(:,4)*TL)+(A1(:,5)*TM)+(A1(:,6)*TH));
for i=1:58
    
    for t=1:12
       qit = ((1/(T.^(1/2))*sqrt(2*pi)))*exp((-1/2)*((A1(:,3)-((qDH*A1(:,6))+(qDL*A1(:,4))).^2)/(T))); %Normal density equation
       B(it) = vec(qit);
       Blog = (-1)*(log(Bit));
       
    end
end
for i=59:176

    for t=1:25
       qit = ((1/(T.^(1/2))*sqrt(2*pi)))*exp((-1/2)*((A59(:,3)-((qDH*A59(:,6))+(qDM*A59(:,5))+(qDL*A59(:,4))).^2)/(T)));
       C(it) = vec(qit); 
       Clog = log(Cit);
    end
end
